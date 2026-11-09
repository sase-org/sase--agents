# Chat History - ace-run (sase-1rq.2.1.4.1.5.3.1.2--mon-3)

- **TIMESTAMP:** 2026-11-09 10:52:14 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1rq.2.1.4.1.5.3.1.2--mon-3

## Prompt

sase monitor start --command 'python -c \'import resource, subprocess, sys, time; start=time.monotonic(); p=subprocess.run(["env", "SASE_CONTENTION_CPUS=0,1", "SASE_CONTENTION_WORKERS=26", "SASE_CONTENTION_REPEAT=1", "just", "test-contention"], check=False); usage=resource.getrusage(resource.RUSAGE_CHILDREN); print(f"RESOURCE child_user_seconds={usage.ru_utime:.2f} child_system_seconds={usage.ru_stime:.2f} max_child_rss_kib={usage.ru_maxrss}", flush=True); print(f"ELAPSED_SECONDS={time.monotonic()-start:.2f}", flush=True); print(f"TEST_EXIT_CODE={p.returncode}", flush=True); sys.exit(p.returncode)\'' --reason 'Run one full 26-worker, two-CPU contention repeat after focused TUI failure repro passed'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.44.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-contention          │
└───────────────────────────────────────────────────────┘

---------- Running default-lane pytest contention harness... ----------
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5671 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 1732096, sampler pid 1732122 on cpus 0-63 (soak cpus 0-1), python 3.14.7, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-1661404-1794234805636142730.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 37.1G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.31 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 297.7G/44912804i tmp 28.2G/993870i workspace 297.7G/44912804i | scratch used 0.1G in 24422 entries (truncated) | progress none yet
[contention-diag] +17s soak 28p/80t rss 2.7G pss 2.4G swap 0.0G majflt 3 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.6G pss 2.3G | host avail 35.0G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.53 cpu 11.82 | cgroup 2.6G/max oom_kill 0 | free scratch 297.7G/44912716i tmp 28.2G/993870i workspace 297.7G/44912716i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +32s soak 28p/80t rss 4.6G pss 4.1G swap 0.0G majflt 4 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.4G pss 4.0G | host avail 36.0G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 2.41 cpu 15.53 | cgroup 4.3G/max oom_kill 0 | free scratch 297.4G/44912296i tmp 28.2G/993868i workspace 297.4G/44912296i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +47s soak 29p/86t rss 5.9G pss 5.4G swap 0.0G majflt 4 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.8G pss 5.3G, 1 descendant rss 0.0G pss 0.0G | host avail 33.5G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.21/0.21 io 2.5 cpu 18.88 | cgroup 5.7G/max oom_kill 0 | free scratch 297.3G/44912292i tmp 28.2G/993870i workspace 297.3G/44912292i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +63s soak 29p/90t rss 7.0G pss 6.4G swap 0.0G majflt 17 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.9G pss 6.3G, 1 descendant rss 0.0G pss 0.0G | host avail 30.6G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.58/0.22 io 2.1 cpu 19.39 | cgroup 6.8G/max oom_kill 0 | free scratch 297.3G/44912262i tmp 28.2G/993869i workspace 297.3G/44912262i | repeat-01 collected 1/26 workers (2332 items) tests 0 done 0 failed
[contention-diag] +78s soak 28p/90t rss 8.0G pss 7.3G swap 0.0G majflt 18 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.2G | host avail 36.6G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.14/0.05 io 2.34 cpu 20.71 | cgroup 7.9G/max oom_kill 0 | free scratch 297.2G/44912245i tmp 28.2G/993869i workspace 297.2G/44912245i | repeat-01 collected 22/26 workers (51561 items) tests 0 done 0 failed
contention shards: 26 workers collected 60629 items in total (2020-2558 per worker)
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
....................[contention-diag] +93s soak 30p/119t rss 8.5G pss 7.8G swap 0.0G majflt 36 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.6G, 2 descendant rss 0.1G pss 0.1G | host avail 33.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.09/0.0 io 3.16 cpu 19.46 | cgroup 8.4G/max oom_kill 0 | free scratch 297.1G/44909840i tmp 28.2G/993869i workspace 297.1G/44909840i | repeat-01 collected 26/26 workers (60629 items) tests 809 done 0 failed | 26 in flight, oldest 11s gw20 tests/ace/test_revert_agent_import_order.py::test_module_imports_first_in_a_fresh_interpreter[sase.ace.revert_agent_resolution]
.................................................... [ 39%]
........................................................................ [ 43%]
........................................................................ [ 46%]
........................................................................ [ 49%]
........................................................................ [ 53%]
....................................[contention-diag] +108s soak 29p/140t rss 8.9G pss 8.1G swap 0.0G majflt 36 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 7.9G, 1 descendant rss 0.1G pss 0.1G | host avail 32.7G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 3.11 cpu 18.71 | cgroup 8.8G/max oom_kill 0 | free scratch 297.1G/44909002i tmp 28.2G/993869i workspace 297.1G/44909002i | repeat-01 collected 26/26 workers (60629 items) tests 1170 done 0 failed | 26 in flight, oldest 26s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
.................................... [ 56%]
........................................................................ [ 59%]
........................................................................ [ 63%]
........................................................................ [ 66%]
..........................[contention-diag] +124s soak 29p/150t rss 9.2G pss 8.3G swap 0.0G majflt 36 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.1G, 1 descendant rss 0.0G pss 0.0G | host avail 33.1G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.59 cpu 15.98 | cgroup 9.0G/max oom_kill 0 | free scratch 297.1G/44908462i tmp 28.2G/993869i workspace 297.1G/44908462i | scratch used 0.3G in 47137 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 1391 done 0 failed | 25 in flight, oldest 41s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
.............................................. [ 69%]
........................................................................ [ 73%]
........................................................................ [ 76%]
........................................................................ [ 79%]
........[contention-diag] +141s soak 31p/166t rss 9.5G pss 8.6G swap 0.0G majflt 37 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.4G, 3 descendant rss 0.2G pss 0.1G | host avail 31.8G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.77 cpu 20.32 | cgroup 9.4G/max oom_kill 0 | free scratch 297.1G/44907564i tmp 28.2G/993869i workspace 297.1G/44907564i | repeat-01 collected 26/26 workers (60629 items) tests 1727 done 0 failed | 26 in flight, oldest 55s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
................................................................ [ 83%]
........................................................................ [ 86%]
.................................[contention-diag] +156s soak 35p/189t rss 9.7G pss 8.8G swap 0.0G majflt 38 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.6G, 7 descendant rss 0.1G pss 0.1G | host avail 31.1G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.84 cpu 21.64 | cgroup 9.5G/max oom_kill 0 | free scratch 297.1G/44907009i tmp 28.2G/993869i workspace 297.1G/44907009i | repeat-01 collected 26/26 workers (60629 items) tests 1898 done 0 failed | 26 in flight, oldest 70s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
....................................... [ 89%]
........................................................................ [ 93%]
..................................................[contention-diag] +171s soak 38p/204t rss 9.9G pss 9.0G swap 0.0G majflt 38 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.7G, 10 descendant rss 0.2G pss 0.1G | host avail 31.8G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 2.9 cpu 17.14 | cgroup 9.7G/max oom_kill 0 | free scratch 296.7G/44906535i tmp 28.2G/993869i workspace 296.7G/44906535i | repeat-01 collected 26/26 workers (60629 items) tests 2060 done 0 failed | 26 in flight, oldest 64s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................... [ 96%]
........................................................................ [ 99%]
........................................................................ [103%]
........................................................................ [106%]
.........................................................[contention-diag] +187s soak 37p/197t rss 10.2G pss 9.2G swap 0.0G majflt 38 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 8.8G, 9 descendant rss 0.3G pss 0.2G | host avail 32.7G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 3.89 cpu 22.19 | cgroup 10.0G/max oom_kill 0 | free scratch 297.1G/44905825i tmp 28.0G/993049i workspace 297.1G/44905825i | repeat-01 collected 26/26 workers (60629 items) tests 2352 done 0 failed | 26 in flight, oldest 79s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............... [109%]
........................................................................ [113%]
........................................................................ [116%]
.....................................................[contention-diag] +202s soak 34p/179t rss 10.2G pss 9.3G swap 0.0G majflt 42 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.0G, 6 descendant rss 0.2G pss 0.1G | host avail 33.1G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.66 cpu 21.54 | cgroup 10.1G/max oom_kill 0 | free scratch 297.1G/44905206i tmp 28.0G/993049i workspace 297.1G/44905206i | repeat-01 collected 26/26 workers (60629 items) tests 2546 done 0 failed | 26 in flight, oldest 94s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................... [119%]
........................................................................ [123%]
.............................................................[contention-diag] +217s soak 36p/199t rss 10.6G pss 9.6G swap 0.0G majflt 46 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.2G, 8 descendant rss 0.4G pss 0.3G | host avail 28.8G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.1 cpu 18.29 | cgroup 10.4G/max oom_kill 0 | free scratch 297.1G/44904653i tmp 28.0G/993049i workspace 297.1G/44904653i | repeat-01 collected 26/26 workers (60629 items) tests 2724 done 0 failed | 26 in flight, oldest 109s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........... [126%]
...................................................................[contention-diag] +232s soak 38p/202t rss 10.9G pss 9.8G swap 0.0G majflt 339 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.3G, 10 descendant rss 0.5G pss 0.4G | host avail 26.0G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.51/0.32 io 2.78 cpu 18.84 | cgroup 10.6G/max oom_kill 0 | free scratch 297.1G/44904372i tmp 28.0G/993049i workspace 297.1G/44904372i | repeat-01 collected 26/26 workers (60629 items) tests 2794 done 0 failed | 26 in flight, oldest 125s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..... [129%]
........................................................................ [133%]
........................................................................ [136%]
........................................................................ [139%]
........................................................................ [143%]
...[contention-diag] +248s soak 35p/193t rss 10.7G pss 9.7G swap 0.0G majflt 69 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.3G, 7 descendant rss 0.3G pss 0.2G | host avail 28.1G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.19/0.15 io 3.31 cpu 19.94 | cgroup 10.5G/max oom_kill 0 | free scratch 297.1G/44903600i tmp 28.0G/993049i workspace 297.1G/44903600i | scratch used 0.3G in 50186 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 3073 done 0 failed | 26 in flight, oldest 140s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................................................... [146%]
..............................................[contention-diag] +265s soak 33p/216t rss 10.6G pss 9.6G swap 0.0G majflt 68 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.4G, 5 descendant rss 0.1G pss 0.0G | host avail 26.9G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 3.37 cpu 21.05 | cgroup 10.5G/max oom_kill 0 | free scratch 297.1G/44903176i tmp 28.0G/993049i workspace 297.1G/44903176i | repeat-01 collected 26/26 workers (60629 items) tests 3214 done 0 failed | 26 in flight, oldest 157s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................[contention-diag] +280s soak 36p/220t rss 10.8G pss 9.8G swap 0.0G majflt 68 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.5G, 8 descendant rss 0.2G pss 0.1G | host avail 23.8G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.56 cpu 18.68 | cgroup 10.7G/max oom_kill 0 | free scratch 297.0G/44903028i tmp 28.0G/993048i workspace 297.0G/44903028i | repeat-01 collected 26/26 workers (60629 items) tests 3233 done 0 failed | 26 in flight, oldest 173s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.... [149%]
................................[contention-diag] +296s soak 34p/217t rss 10.8G pss 9.8G swap 0.0G majflt 69 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.6G, 6 descendant rss 0.1G pss 0.1G | host avail 24.9G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 1.7 cpu 15.07 | cgroup 10.1G/max oom_kill 0 | free scratch 296.7G/44902772i tmp 28.0G/993047i workspace 296.7G/44902772i | repeat-01 collected 26/26 workers (60629 items) tests 3266 done 0 failed | 26 in flight, oldest 188s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................ [152%]
........................................................................ [156%]
..............[contention-diag] +311s soak 33p/210t rss 10.8G pss 9.9G swap 0.0G majflt 75 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 5 descendant rss 0.1G pss 0.0G | host avail 28.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.78/0.77 io 2.39 cpu 17.17 | cgroup 10.2G/max oom_kill 0 | free scratch 296.6G/44902350i tmp 28.0G/993047i workspace 296.6G/44902350i | repeat-01 collected 26/26 workers (60629 items) tests 3396 done 0 failed | 26 in flight, oldest 203s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................................................... [159%]
..........................................................[contention-diag] +326s soak 35p/206t rss 10.9G pss 10.0G swap 0.0G majflt 82 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 7 descendant rss 0.2G pss 0.1G | host avail 28.4G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 2.15 cpu 14.59 | cgroup 10.3G/max oom_kill 0 | free scratch 296.3G/44901955i tmp 28.0G/993047i workspace 296.3G/44901955i | repeat-01 collected 26/26 workers (60629 items) tests 3505 done 0 failed | 26 in flight, oldest 219s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............. [162%]
........................................................................ [166%]
................................[contention-diag] +342s soak 34p/218t rss 11.0G pss 10.0G swap 0.0G majflt 82 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 6 descendant rss 0.1G pss 0.1G | host avail 32.7G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 2.95 cpu 18.62 | cgroup 10.3G/max oom_kill 0 | free scratch 296.7G/44901622i tmp 28.0G/993049i workspace 296.7G/44901622i | repeat-01 collected 26/26 workers (60629 items) tests 3631 done 0 failed | 26 in flight, oldest 234s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...........................[contention-diag] +357s soak 35p/216t rss 11.1G pss 10.1G swap 0.0G majflt 82 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 7 descendant rss 0.2G pss 0.1G | host avail 30.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.3 cpu 20.1 | cgroup 10.4G/max oom_kill 0 | free scratch 296.7G/44901421i tmp 28.0G/993049i workspace 296.7G/44901421i | repeat-01 collected 26/26 workers (60629 items) tests 3656 done 0 failed | 26 in flight, oldest 249s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............. [169%]
........................................................................ [172%]
...........................[contention-diag] +372s soak 38p/221t rss 11.1G pss 10.1G swap 0.0G majflt 91 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G, 10 descendant rss 0.1G pss 0.0G | host avail 29.4G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.35/0.35 io 3.19 cpu 17.11 | cgroup 10.4G/max oom_kill 0 | free scratch 296.7G/44901032i tmp 28.0G/993049i workspace 296.7G/44901032i | scratch used 0.2G in 36578 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 3768 done 0 failed | 26 in flight, oldest 265s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................. [176%]
.............................................................[contention-diag] +390s soak 39p/219t rss 11.3G pss 10.2G swap 0.0G majflt 95 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 9.9G, 11 descendant rss 0.2G pss 0.1G | host avail 28.1G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 3.36 cpu 16.19 | cgroup 10.6G/max oom_kill 0 | free scratch 296.7G/44900708i tmp 28.0G/993050i workspace 296.7G/44900708i | repeat-01 collected 26/26 workers (60629 items) tests 3875 done 0 failed | 26 in flight, oldest 282s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........... [179%]
.................................................................[contention-diag] +405s soak 42p/235t rss 11.4G pss 10.3G swap 0.0G majflt 96 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 14 descendant rss 0.3G pss 0.2G | host avail 24.3G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.85 cpu 16.94 | cgroup 10.7G/max oom_kill 0 | free scratch 296.7G/44900349i tmp 28.0G/993049i workspace 296.7G/44900349i | repeat-01 collected 26/26 workers (60629 items) tests 3949 done 0 failed | 26 in flight, oldest 297s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....... [182%]
........................................................................ [186%]
......................[contention-diag] +420s soak 40p/216t rss 11.4G pss 10.3G swap 0.0G majflt 95 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 12 descendant rss 0.3G pss 0.2G | host avail 26.1G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.36 cpu 13.76 | cgroup 10.7G/max oom_kill 0 | free scratch 296.7G/44900036i tmp 28.0G/993049i workspace 296.7G/44900036i | repeat-01 collected 26/26 workers (60629 items) tests 4036 done 0 failed | 26 in flight, oldest 313s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................. [189%]
...........................[contention-diag] +436s soak 37p/217t rss 11.3G pss 10.3G swap 0.0G majflt 98 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 9 descendant rss 0.1G pss 0.1G | host avail 29.4G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 2.12 cpu 15.37 | cgroup 10.7G/max oom_kill 0 | free scratch 297.1G/44900079i tmp 28.0G/993049i workspace 297.1G/44900079i | repeat-01 collected 26/26 workers (60629 items) tests 4127 done 0 failed | 25 in flight, oldest 328s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................. [192%]
........................................................................ [196%]
...........[contention-diag] +451s soak 35p/218t rss 11.3G pss 10.3G swap 0.0G majflt 114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 7 descendant rss 0.2G pss 0.1G | host avail 29.3G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.22 cpu 16.87 | cgroup 10.8G/max oom_kill 0 | free scratch 297.1G/44899655i tmp 28.0G/993049i workspace 297.1G/44899655i | repeat-01 collected 26/26 workers (60629 items) tests 4259 done 0 failed | 26 in flight, oldest 343s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...........................................................[contention-diag] +466s soak 30p/208t rss 11.4G pss 10.4G swap 0.0G majflt 116 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 2 descendant rss 0.2G pss 0.2G | host avail 27.1G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.37 cpu 15.32 | cgroup 10.9G/max oom_kill 0 | free scratch 297.1G/44899345i tmp 28.0G/993049i workspace 297.1G/44899345i | repeat-01 collected 26/26 workers (60629 items) tests 4315 done 0 failed | 26 in flight, oldest 359s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.. [199%]
........................................................................ [202%]
.................[contention-diag] +482s soak 29p/209t rss 11.4G pss 10.4G swap 0.0G majflt 115 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 1 descendant rss 0.1G pss 0.1G | host avail 30.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.55 cpu 19.5 | cgroup 10.8G/max oom_kill 0 | free scratch 297.1G/44899043i tmp 28.0G/993050i workspace 297.1G/44899043i | repeat-01 collected 26/26 workers (60629 items) tests 4407 done 0 failed | 26 in flight, oldest 374s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................[contention-diag] +497s soak 29p/227t rss 11.4G pss 10.4G swap 0.0G majflt 116 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 25.8G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.38 cpu 16.67 | cgroup 10.9G/max oom_kill 0 | free scratch 296.8G/44898682i tmp 28.0G/993050i workspace 296.8G/44898682i | scratch used 0.3G in 61216 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 4451 done 0 failed | 26 in flight, oldest 389s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........... [206%]
.......[contention-diag] +514s soak 29p/225t rss 11.4G pss 10.4G swap 0.0G majflt 119 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.3G, 1 descendant rss 0.1G pss 0.0G | host avail 31.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 13.6 | cgroup 11.0G/max oom_kill 0 | free scratch 298.7G/44922927i tmp 28.0G/993048i workspace 298.7G/44922927i | repeat-01 collected 26/26 workers (60629 items) tests 4463 done 0 failed | 26 in flight, oldest 51s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
......................................[contention-diag] +530s soak 31p/216t rss 11.6G pss 10.6G swap 0.0G majflt 307 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 10.3G, 3 descendant rss 0.2G pss 0.1G | host avail 28.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 16.41 | cgroup 11.1G/max oom_kill 0 | free scratch 298.9G/44909736i tmp 28.0G/993050i workspace 298.9G/44909736i | repeat-01 collected 26/26 workers (60629 items) tests 4506 done 0 failed | 26 in flight, oldest 67s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
........................... [209%]
...........[contention-diag] +545s soak 28p/230t rss 11.5G pss 10.5G swap 0.0G majflt 132 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.3G | host avail 26.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.32 | cgroup 11.1G/max oom_kill 0 | free scratch 298.9G/44909534i tmp 28.0G/993050i workspace 298.9G/44909534i | repeat-01 collected 26/26 workers (60629 items) tests 4547 done 0 failed | 26 in flight, oldest 79s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
............................................................. [212%]
.....[contention-diag] +560s soak 29p/220t rss 11.6G pss 10.6G swap 0.0G majflt 132 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G, 1 descendant rss 0.1G pss 0.1G | host avail 25.0G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.2 | cgroup 11.2G/max oom_kill 0 | free scratch 298.9G/44909197i tmp 28.0G/993050i workspace 298.9G/44909197i | repeat-01 collected 26/26 workers (60629 items) tests 4608 done 0 failed | 26 in flight, oldest 94s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
............................................................[contention-diag] +576s soak 29p/218t rss 11.6G pss 10.6G swap 0.0G majflt 136 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 27.1G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 15.01 | cgroup 11.2G/max oom_kill 0 | free scratch 298.4G/44908846i tmp 28.0G/993050i workspace 298.4G/44908846i | repeat-01 collected 26/26 workers (60629 items) tests 4669 done 0 failed | 26 in flight, oldest 48s gw25 tests/ace/tui/test_link_follow_entry_points.py::test_matrix_links_panel_key_path_follows_first_chip
....... [216%]
.........................................[contention-diag] +591s soak 28p/221t rss 11.6G pss 10.6G swap 0.0G majflt 136 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.4G | host avail 27.1G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 18.35 | cgroup 11.2G/max oom_kill 0 | free scratch 298.5G/44905202i tmp 28.0G/993050i workspace 298.5G/44905202i | repeat-01 collected 26/26 workers (60629 items) tests 4720 done 0 failed | 26 in flight, oldest 51s gw22 tests/ace/tui/test_artifacts_beads_filtering.py::test_hide_closed_default_is_visible_and_clearable
.........................[contention-diag] +606s soak 29p/219t rss 11.6G pss 10.6G swap 0.0G majflt 136 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 26.7G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 16.54 | cgroup 11.2G/max oom_kill 0 | free scratch 298.2G/44905015i tmp 28.0G/993050i workspace 298.2G/44905015i | repeat-01 collected 26/26 workers (60629 items) tests 4745 done 0 failed | 26 in flight, oldest 54s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
...... [219%]
.......................................[contention-diag] +622s soak 30p/232t rss 11.8G pss 10.8G swap 0.0G majflt 136 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.5G, 2 descendant rss 0.1G pss 0.1G | host avail 31.6G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 17.14 | cgroup 11.4G/max oom_kill 0 | free scratch 298.3G/44916844i tmp 28.0G/993050i workspace 298.3G/44916844i | scratch used 0.4G in 75474 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 4788 done 0 failed | 26 in flight, oldest 69s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
................................. [222%]
..[contention-diag] +639s soak 28p/230t rss 11.7G pss 10.7G swap 0.0G majflt 136 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.5G | host avail 28.3G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 18.03 | cgroup 11.4G/max oom_kill 0 | free scratch 298.3G/44916503i tmp 28.0G/993049i workspace 298.3G/44916503i | repeat-01 collected 26/26 workers (60629 items) tests 4823 done 0 failed | 26 in flight, oldest 75s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
.............................[contention-diag] +654s soak 29p/230t rss 11.7G pss 10.7G swap 0.0G majflt 137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 27.7G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.92 | cgroup 11.4G/max oom_kill 0 | free scratch 298.1G/44915966i tmp 28.0G/993049i workspace 298.1G/44915966i | repeat-01 collected 26/26 workers (60629 items) tests 4851 done 0 failed | 26 in flight, oldest 77s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
..............................[contention-diag] +670s soak 30p/236t rss 11.8G pss 10.8G swap 0.0G majflt 142 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.6G, 2 descendant rss 0.1G pss 0.1G | host avail 28.1G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 20.14 | cgroup 11.5G/max oom_kill 0 | free scratch 297.8G/44915751i tmp 28.0G/993049i workspace 297.8G/44915751i | repeat-01 collected 26/26 workers (60629 items) tests 4884 done 0 failed | 26 in flight, oldest 59s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
..........[contention-diag] +685s soak 29p/225t rss 11.9G pss 10.9G swap 0.0G majflt 140 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.6G, 1 descendant rss 0.1G pss 0.1G | host avail 27.2G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 20.47 | cgroup 11.6G/max oom_kill 0 | free scratch 297.5G/44915420i tmp 28.0G/993049i workspace 297.5G/44915420i | repeat-01 collected 26/26 workers (60629 items) tests 4893 done 0 failed | 26 in flight, oldest 48s gw13 tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_real_R_press_reruns_declined_and_notices_otherwise
. [226%]
.................................[contention-diag] +700s soak 29p/216t rss 11.8G pss 10.8G swap 0.0G majflt 140 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 30.8G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.56 | cgroup 11.7G/max oom_kill 0 | free scratch 297.4G/44914849i tmp 28.0G/993049i workspace 297.4G/44914848i | repeat-01 collected 26/26 workers (60629 items) tests 4923 done 0 failed | 26 in flight, oldest 60s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
....................................... [229%]
........................................................................ [232%]
...[contention-diag] +716s soak 29p/216t rss 11.9G pss 10.9G swap 0.0G majflt 141 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.7G, 1 descendant rss 0.1G pss 0.1G | host avail 31.5G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.0 | cgroup 11.7G/max oom_kill 0 | free scratch 297.4G/44914468i tmp 28.0G/993049i workspace 297.4G/44914468i | repeat-01 collected 26/26 workers (60629 items) tests 5038 done 0 failed | 26 in flight, oldest 60s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_panel_action_override_takes_effect_in_mounted_pilot
........................................[contention-diag] +731s soak 29p/217t rss 11.9G pss 10.9G swap 0.0G majflt 141 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.6 cpu 24.69 | cgroup 11.8G/max oom_kill 0 | free scratch 297.4G/44914117i tmp 28.0G/993049i workspace 297.4G/44914117i | repeat-01 collected 26/26 workers (60629 items) tests 5083 done 0 failed | 26 in flight, oldest 49s gw0 tests/ace/tui/test_copy_as_palette_entrypoints.py::test_percent_opens_palette_for_each_live_artifacts_subtab[ref:plan]
............................. [236%]
........................................................................ [239%]
........................................................................ [242%]
........................................................................ [246%]
........................................................................ [249%]
..............................[contention-diag] +746s soak 28p/212t rss 11.9G pss 10.9G swap 0.0G majflt 141 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.7G | host avail 32.3G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.19/0.19 io 0.27 cpu 25.66 | cgroup 11.6G/max oom_kill 0 | free scratch 297.4G/44912989i tmp 28.0G/993049i workspace 297.4G/44912989i | scratch used 0.5G in 87984 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 5392 done 0 failed | 25 in flight, oldest 58s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
.......................................... [252%]
.......................................................[contention-diag] +764s soak 31p/230t rss 12.0G pss 11.0G swap 0.0G majflt 144 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 31.8G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.14 cpu 25.61 | cgroup 11.8G/max oom_kill 0 | free scratch 297.4G/44912445i tmp 28.0G/993049i workspace 297.4G/44912445i | repeat-01 collected 26/26 workers (60629 items) tests 5517 done 0 failed | 26 in flight, oldest 61s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
................. [256%]
.......................................................[contention-diag] +779s soak 32p/227t rss 12.0G pss 11.0G swap 0.0G majflt 145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.8G pss 10.8G, 4 descendant rss 0.1G pss 0.1G | host avail 32.9G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 24.04 | cgroup 11.8G/max oom_kill 0 | free scratch 297.3G/44912094i tmp 28.0G/993049i workspace 297.3G/44912094i | repeat-01 collected 26/26 workers (60629 items) tests 5596 done 0 failed | 26 in flight, oldest 75s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
................. [259%]
...........................................................[contention-diag] +795s soak 28p/221t rss 12.0G pss 11.0G swap 0.0G majflt 146 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.8G pss 10.9G | host avail 32.2G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 27.38 | cgroup 11.9G/max oom_kill 0 | free scratch 297.3G/44911790i tmp 28.0G/993049i workspace 297.3G/44911790i | repeat-01 collected 26/26 workers (60629 items) tests 5674 done 0 failed | 26 in flight, oldest 90s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............. [262%]
......[contention-diag] +810s soak 29p/231t rss 12.1G pss 11.1G swap 0.0G majflt 146 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.27 | cgroup 12.1G/max oom_kill 0 | free scratch 297.3G/44911594i tmp 28.0G/993049i workspace 297.3G/44911594i | repeat-01 collected 26/26 workers (60629 items) tests 5692 done 0 failed | 26 in flight, oldest 106s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.........................[contention-diag] +825s soak 31p/247t rss 12.2G pss 11.1G swap 0.0G majflt 146 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.9G pss 10.9G, 3 descendant rss 0.1G pss 0.0G | host avail 31.1G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.37 | cgroup 12.1G/max oom_kill 0 | free scratch 297.4G/44911888i tmp 28.0G/993049i workspace 297.4G/44911888i | repeat-01 collected 26/26 workers (60629 items) tests 5707 done 0 failed | 26 in flight, oldest 121s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
......................................... [266%]
.............................................................[contention-diag] +840s soak 28p/232t rss 12.1G pss 11.1G swap 0.0G majflt 146 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.9G pss 11.0G | host avail 30.9G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.78 | cgroup 11.9G/max oom_kill 0 | free scratch 297.4G/44911019i tmp 28.0G/993049i workspace 297.4G/44911019i | repeat-01 collected 26/26 workers (60629 items) tests 5819 done 0 failed | 26 in flight, oldest 136s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........... [269%]
........................................................................ [272%]
...................[contention-diag] +856s soak 31p/234t rss 12.2G pss 11.2G swap 0.0G majflt 147 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.0G pss 11.0G, 3 descendant rss 0.0G pss 0.0G | host avail 28.5G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.85 | cgroup 12.0G/max oom_kill 0 | free scratch 297.1G/44910610i tmp 28.0G/993049i workspace 297.1G/44910610i | repeat-01 collected 26/26 workers (60629 items) tests 5916 done 0 failed | 26 in flight, oldest 152s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
..................................................... [276%]
........................................................................ [279%]
........................................................................ [282%]
........................................................................ [286%]
......................................[contention-diag] +871s soak 28p/198t rss 12.2G pss 11.2G swap 0.0G majflt 147 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.0G pss 11.0G | host avail 29.7G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.0 cpu 17.87 | cgroup 12.0G/max oom_kill 0 | free scratch 297.3G/44909753i tmp 28.0G/993049i workspace 297.3G/44909753i | scratch used 0.5G in 99604 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 6190 done 0 failed | 26 in flight, oldest 80s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_toggle_clamps_container_and_restores_width
.................................. [289%]
.................................................................[contention-diag] +889s soak 29p/229t rss 12.3G pss 11.3G swap 0.0G majflt 150 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.0G pss 11.1G, 1 descendant rss 0.1G pss 0.1G | host avail 30.8G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.26 cpu 17.99 | cgroup 12.2G/max oom_kill 0 | free scratch 303.4G/44934635i tmp 28.0G/993049i workspace 303.4G/44934635i | repeat-01 collected 26/26 workers (60629 items) tests 6322 done 0 failed | 26 in flight, oldest 77s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
....... [292%]
...........................................[contention-diag] +904s soak 29p/218t rss 12.3G pss 11.3G swap 0.0G majflt 160 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.1G pss 11.1G, 1 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 16.72 | cgroup 12.1G/max oom_kill 0 | free scratch 303.4G/44934419i tmp 28.0G/993049i workspace 303.4G/44934419i | repeat-01 collected 26/26 workers (60629 items) tests 6378 done 0 failed | 26 in flight, oldest 54s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_during_committed_search_exits_and_opens_picker
............................. [295%]
..................................................[contention-diag] +920s soak 28p/218t rss 12.3G pss 11.3G swap 0.0G majflt 162 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.1G pss 11.1G | host avail 28.8G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 17.68 | cgroup 12.2G/max oom_kill 0 | free scratch 303.4G/44934140i tmp 28.0G/993049i workspace 303.4G/44934140i | repeat-01 collected 26/26 workers (60629 items) tests 6455 done 0 failed | 25 in flight, oldest 69s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_during_committed_search_exits_and_opens_picker
...................... [299%]
........................................................................ [302%]
..........[contention-diag] +935s soak 28p/220t rss 12.3G pss 11.3G swap 0.0G majflt 169 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.1G pss 11.1G | host avail 30.3G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.17 | cgroup 12.2G/max oom_kill 0 | free scratch 303.4G/44933799i tmp 28.0G/993049i workspace 303.4G/44933799i | repeat-01 collected 26/26 workers (60629 items) tests 6561 done 0 failed | 26 in flight, oldest 63s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
.............................................................. [305%]
..................................................................[contention-diag] +950s soak 28p/211t rss 12.4G pss 11.4G swap 0.0G majflt 169 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.2G pss 11.2G | host avail 27.8G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.32 cpu 18.08 | cgroup 12.3G/max oom_kill 0 | free scratch 303.4G/44933918i tmp 28.0G/993049i workspace 303.4G/44933918i | repeat-01 collected 26/26 workers (60629 items) tests 6684 done 0 failed | 25 in flight, oldest 51s gw24 tests/ace/tui/test_config_center_resume.py::test_blocked_write_keeps_navigation_responsive_and_persists_latest
...... [309%]
...................................[contention-diag] +966s soak 28p/215t rss 12.4G pss 11.4G swap 0.0G majflt 169 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G | host avail 30.5G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 18.07 | cgroup 12.3G/max oom_kill 0 | free scratch 303.4G/44932849i tmp 28.0G/993049i workspace 303.4G/44932849i | repeat-01 collected 26/26 workers (60629 items) tests 6730 done 0 failed | 26 in flight, oldest 47s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_clicking_idle_file_bar_opens_the_filter_session
..................................... [312%]
..........................[contention-diag] +981s soak 28p/207t rss 12.4G pss 11.4G swap 0.0G majflt 171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.2G pss 11.2G | host avail 30.7G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 17.07 | cgroup 12.3G/max oom_kill 0 | free scratch 303.4G/44932546i tmp 28.0G/993049i workspace 303.4G/44932546i | repeat-01 collected 26/26 workers (60629 items) tests 6786 done 0 failed | 26 in flight, oldest 54s gw3 tests/ace/tui/test_artifacts_limit_keys.py::test_beads_ctrl_j_grows_limit_and_ctrl_k_returns_to_floor
.............................................. [315%]
......................................................[contention-diag] +996s soak 30p/214t rss 12.5G pss 11.5G swap 0.0G majflt 171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 2 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.0 cpu 19.44 | cgroup 12.4G/max oom_kill 0 | free scratch 304.2G/44940331i tmp 28.0G/993049i workspace 304.2G/44940331i | scratch used 0.6G in 111002 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 6863 done 0 failed | 26 in flight, oldest 58s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
.................. [319%]
........................................................................ [322%]
........................[contention-diag] +1014s soak 30p/220t rss 12.5G pss 11.5G swap 0.0G majflt 171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 2 descendant rss 0.1G pss 0.1G | host avail 29.5G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.22 cpu 20.98 | cgroup 12.4G/max oom_kill 0 | free scratch 304.2G/44939912i tmp 28.0G/993049i workspace 304.2G/44939912i | repeat-01 collected 26/26 workers (60629 items) tests 7007 done 0 failed | 26 in flight, oldest 75s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
................................................ [325%]
........................[contention-diag] +1029s soak 29p/205t rss 12.6G pss 11.5G swap 0.0G majflt 171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 1 descendant rss 0.1G pss 0.1G | host avail 27.8G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 17.81 | cgroup 12.5G/max oom_kill 0 | free scratch 304.1G/44938124i tmp 28.0G/993026i workspace 304.1G/44938124i | repeat-01 collected 26/26 workers (60629 items) tests 7078 done 0 failed | 25 in flight, oldest 51s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_t_in_left_right_split_fills_left_panel
................................................ [329%]
........................................................................ [332%]
........................[contention-diag] +1044s soak 30p/219t rss 12.7G pss 11.6G swap 0.0G majflt 171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G, 2 descendant rss 0.1G pss 0.1G | host avail 27.7G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 2.07/1.77 io 0.2 cpu 14.5 | cgroup 12.5G/max oom_kill 0 | free scratch 304.0G/44936135i tmp 28.0G/993025i workspace 304.0G/44936135i | repeat-01 collected 26/26 workers (60629 items) tests 7223 done 0 failed | 26 in flight, oldest 67s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_capital_t_in_left_right_split_fills_left_panel
................................................ [335%]
........................[contention-diag] +1060s soak 28p/218t rss 12.5G pss 11.5G swap 0.0G majflt 171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G | host avail 29.6G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.41/0.35 io 0.04 cpu 16.39 | cgroup 12.4G/max oom_kill 0 | free scratch 303.7G/44935907i tmp 28.0G/993028i workspace 303.7G/44935907i | repeat-01 collected 26/26 workers (60629 items) tests 7291 done 0 failed | 26 in flight, oldest 73s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
................................................ [339%]
........................................................................ [342%]
..[contention-diag] +1075s soak 28p/221t rss 12.5G pss 11.5G swap 0.0G majflt 177 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.3G pss 11.3G | host avail 31.2G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.08/0.07 io 0.17 cpu 17.74 | cgroup 12.5G/max oom_kill 0 | free scratch 303.6G/44933300i tmp 28.0G/993007i workspace 303.6G/44933300i | repeat-01 collected 26/26 workers (60629 items) tests 7417 done 0 failed | 26 in flight, oldest 60s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
...................................................................... [345%]
........[contention-diag] +1090s soak 28p/232t rss 12.6G pss 11.5G swap 0.0G majflt 177 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G | host avail 31.4G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.04 cpu 17.75 | cgroup 12.5G/max oom_kill 0 | free scratch 303.6G/44926797i tmp 28.0G/993010i workspace 303.6G/44926797i | repeat-01 collected 26/26 workers (60629 items) tests 7493 done 0 failed | 26 in flight, oldest 75s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_split_in_rail_keeps_rail
................................................................ [349%]
........................................................................ [352%]
..................................[contention-diag] +1106s soak 28p/235t rss 12.6G pss 11.5G swap 0.0G majflt 179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G | host avail 30.8G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 22.39 | cgroup 12.5G/max oom_kill 0 | free scratch 303.5G/44914123i tmp 28.0G/993010i workspace 303.5G/44914123i | repeat-01 collected 26/26 workers (60629 items) tests 7659 done 0 failed | 26 in flight, oldest 76s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
...................................... [355%]
.....................[contention-diag] +1121s soak 38p/259t rss 12.7G pss 11.6G swap 0.0G majflt 179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 10 descendant rss 0.1G pss 0.0G | host avail 28.6G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 17.28 | cgroup 12.6G/max oom_kill 0 | free scratch 304.1G/44912344i tmp 28.0G/993009i workspace 304.1G/44912344i | scratch used 0.7G in 120168 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 7722 done 0 failed | 26 in flight, oldest 76s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
............................................[contention-diag] +1138s soak 40p/249t rss 12.7G pss 11.6G swap 0.0G majflt 180 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 12 descendant rss 0.1G pss 0.0G | host avail 26.1G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 15.9 | cgroup 12.6G/max oom_kill 0 | free scratch 303.8G/44911740i tmp 28.0G/993009i workspace 303.8G/44911740i | repeat-01 collected 26/26 workers (60629 items) tests 7768 done 0 failed | 26 in flight, oldest 93s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
....... [359%]
..[contention-diag] +1154s soak 38p/250t rss 12.7G pss 11.6G swap 0.0G majflt 180 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 10 descendant rss 0.1G pss 0.0G | host avail 24.4G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 17.16 | cgroup 12.6G/max oom_kill 0 | free scratch 303.3G/44911595i tmp 28.0G/993009i workspace 303.3G/44911595i | repeat-01 collected 26/26 workers (60629 items) tests 7778 done 0 failed | 26 in flight, oldest 108s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
...........................[contention-diag] +1169s soak 38p/249t rss 12.7G pss 11.6G swap 0.0G majflt 180 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 10 descendant rss 0.1G pss 0.0G | host avail 21.4G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 0.0 cpu 17.48 | cgroup 12.6G/max oom_kill 0 | free scratch 303.2G/44911452i tmp 28.0G/993009i workspace 303.2G/44911452i | repeat-01 collected 26/26 workers (60629 items) tests 7802 done 0 failed | 26 in flight, oldest 78s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_from_rail_is_flush_and_restores_rail
........................................... [362%]
.............................................................[contention-diag] +1185s soak 38p/234t rss 12.8G pss 11.6G swap 0.0G majflt 260 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.4G pss 11.4G, 10 descendant rss 0.1G pss 0.0G | host avail 19.1G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.8/0.32 io 0.18 cpu 16.48 | cgroup 12.1G/max oom_kill 0 | free scratch 303.0G/44911003i tmp 28.0G/993007i workspace 303.0G/44911003i | repeat-01 collected 26/26 workers (60629 items) tests 7907 done 0 failed | 26 in flight, oldest 57s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
.......[contention-diag] +1200s soak 38p/249t rss 12.8G pss 11.7G swap 0.0G majflt 320 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.4G, 10 descendant rss 0.1G pss 0.0G | host avail 20.3G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.2/0.06 io 0.12 cpu 14.48 | cgroup 12.1G/max oom_kill 0 | free scratch 302.6G/44910474i tmp 28.0G/991689i workspace 302.6G/44910474i | repeat-01 collected 26/26 workers (60629 items) tests 7915 done 0 failed | 26 in flight, oldest 72s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_commits_fast_navigation_skips_day_banners_and_jumps_without_opening
.... [365%]
........................................................................ [369%]
.......................................[contention-diag] +1216s soak 39p/235t rss 12.8G pss 11.7G swap 0.0G majflt 387 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 11 descendant rss 0.1G pss 0.0G | host avail 20.2G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.31/0.13 io 0.02 cpu 16.02 | cgroup 12.1G/max oom_kill 0 | free scratch 302.4G/44910071i tmp 28.0G/991689i workspace 302.4G/44910071i | repeat-01 collected 26/26 workers (60629 items) tests 8029 done 0 failed | 25 in flight, oldest 46s gw9 tests/ace/tui/test_config_center_alternate_tab.py::test_alternate_opener_ping_pongs_between_exactly_two_sections
................................. [372%]
........................[contention-diag] +1231s soak 38p/227t rss 12.8G pss 11.7G swap 0.0G majflt 423 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G, 10 descendant rss 0.1G pss 0.0G | host avail 24.9G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.07/0.03 io 0.22 cpu 19.84 | cgroup 12.1G/max oom_kill 0 | free scratch 302.2G/44909605i tmp 28.0G/991542i workspace 302.2G/44909605i | repeat-01 collected 26/26 workers (60629 items) tests 8082 done 0 failed | 26 in flight, oldest 57s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................................................ [375%]
........................................................................ [379%]
........................................................................ [382%]
....................................[contention-diag] +1246s soak 28p/227t rss 12.7G pss 11.6G swap 0.0G majflt 444 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G | host avail 28.8G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.04 cpu 13.36 | cgroup 12.1G/max oom_kill 0 | free scratch 301.6G/44907810i tmp 28.0G/991537i workspace 301.6G/44907810i | scratch used 0.2G in 34230 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 8260 done 0 failed | 26 in flight, oldest 73s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................... [385%]
........................................................................ [389%]
.........[contention-diag] +1264s soak 28p/219t rss 12.7G pss 11.7G swap 0.0G majflt 448 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G | host avail 27.5G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 16.3 | cgroup 12.2G/max oom_kill 0 | free scratch 301.3G/44907130i tmp 28.0G/991691i workspace 301.3G/44907130i | repeat-01 collected 26/26 workers (60629 items) tests 8419 done 0 failed | 25 in flight, oldest 90s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................................................... [392%]
........................................................................ [395%]
.....[contention-diag] +1279s soak 28p/222t rss 12.7G pss 11.7G swap 0.0G majflt 456 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G | host avail 26.3G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 18.91 | cgroup 12.2G/max oom_kill 0 | free scratch 301.3G/44906700i tmp 28.0G/991693i workspace 301.3G/44906700i | repeat-01 collected 26/26 workers (60629 items) tests 8567 done 0 failed | 26 in flight, oldest 105s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................................................................... [399%]
.........................[contention-diag] +1294s soak 29p/232t rss 12.8G pss 11.7G swap 0.0G majflt 476 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 1 descendant rss 0.0G pss 0.0G | host avail 26.3G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.48/0.0 io 0.0 cpu 21.53 | cgroup 12.3G/max oom_kill 0 | free scratch 301.3G/44906412i tmp 27.9G/991299i workspace 301.3G/44906412i | repeat-01 collected 26/26 workers (60629 items) tests 8664 done 0 failed | 26 in flight, oldest 121s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................................... [402%]
..................................[contention-diag] +1310s soak 30p/213t rss 12.9G pss 11.7G swap 0.0G majflt 480 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.5G, 2 descendant rss 0.2G pss 0.0G | host avail 23.7G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.36/0.0 io 0.0 cpu 22.24 | cgroup 12.3G/max oom_kill 0 | free scratch 301.2G/44906128i tmp 26.8G/988076i workspace 301.2G/44906128i | repeat-01 collected 26/26 workers (60629 items) tests 8745 done 0 failed | 26 in flight, oldest 136s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
...................................... [405%]
........................................................................ [409%]
........................................................................ [412%]
...................[contention-diag] +1325s soak 28p/223t rss 12.7G pss 11.7G swap 0.0G majflt 483 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.5G | host avail 20.0G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 0.0 cpu 19.91 | cgroup 12.3G/max oom_kill 0 | free scratch 301.2G/44905599i tmp 26.1G/986011i workspace 301.2G/44905599i | repeat-01 collected 26/26 workers (60629 items) tests 8940 done 0 failed | 26 in flight, oldest 151s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
..................................................[contention-diag] +1340s soak 28p/225t rss 12.7G pss 11.7G swap 0.0G majflt 492 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G | host avail 21.0G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.16/0.14 io 0.0 cpu 18.9 | cgroup 12.3G/max oom_kill 0 | free scratch 300.9G/44905367i tmp 26.1G/985838i workspace 300.9G/44905367i | repeat-01 collected 26/26 workers (60629 items) tests 8997 done 0 failed | 26 in flight, oldest 166s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
... [415%]
........................................................................ [419%]
..................[contention-diag] +1356s soak 29p/234t rss 12.8G pss 11.8G swap 0.0G majflt 495 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 1 descendant rss 0.0G pss 0.0G | host avail 22.7G/62.7G swapfree 53.3G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 0.18 cpu 19.14 | cgroup 12.4G/max oom_kill 0 | free scratch 299.4G/44905060i tmp 26.1G/985834i workspace 299.4G/44905060i | repeat-01 collected 26/26 workers (60629 items) tests 9069 done 0 failed | 26 in flight, oldest 54s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_patches_pane_sync_triggers_project_inventory
...................................................... [422%]
...................[contention-diag] +1371s soak 28p/232t rss 12.8G pss 11.8G swap 0.0G majflt 503 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G | host avail 22.4G/62.7G swapfree 52.7G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 3.27 cpu 14.05 | cgroup 12.4G/max oom_kill 0 | free scratch 299.7G/44954691i tmp 26.1G/986010i workspace 299.7G/44954691i | scratch used 0.4G in 79598 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 9156 done 0 failed | 26 in flight, oldest 62s gw12 tests/ace/tui/test_feature_flags_pane.py::test_no_match_and_empty_catalog_cards
..................................................... [425%]
...[contention-diag] +1388s soak 29p/230t rss 12.8G pss 11.8G swap 0.0G majflt 519 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.6G, 1 descendant rss 0.0G pss 0.0G | host avail 25.9G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.42/0.42 io 1.33 cpu 9.24 | cgroup 12.5G/max oom_kill 0 | free scratch 299.9G/44953428i tmp 26.1G/986016i workspace 299.9G/44953428i | repeat-01 collected 26/26 workers (60629 items) tests 9218 done 0 failed | 26 in flight, oldest 80s gw12 tests/ace/tui/test_feature_flags_pane.py::test_no_match_and_empty_catalog_cards
..........................[contention-diag] +1404s soak 29p/238t rss 12.8G pss 11.8G swap 0.0G majflt 526 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G, 1 descendant rss 0.0G pss 0.0G | host avail 25.3G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.56 cpu 14.53 | cgroup 12.5G/max oom_kill 0 | free scratch 299.9G/44943947i tmp 26.1G/986017i workspace 299.9G/44943946i | repeat-01 collected 26/26 workers (60629 items) tests 9244 done 0 failed | 26 in flight, oldest 90s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
........................................... [429%]
...[contention-diag] +1420s soak 28p/221t rss 12.8G pss 11.8G swap 0.0G majflt 531 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.7G | host avail 25.6G/62.7G swapfree 52.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 10.09 cpu 13.29 | cgroup 12.5G/max oom_kill 0 | free scratch 299.5G/44924214i tmp 26.1G/985735i workspace 299.5G/44924214i | repeat-01 collected 26/26 workers (60629 items) tests 9287 done 0 failed | 26 in flight, oldest 105s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..................................[contention-diag] +1435s soak 28p/226t rss 12.8G pss 11.8G swap 0.1G majflt 1682 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.6G | host avail 26.7G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 6.21/4.41 io 10.54 cpu 10.39 | cgroup 12.5G/max oom_kill 0 | free scratch 299.3G/44922988i tmp 26.1G/985962i workspace 299.3G/44922988i | repeat-01 collected 26/26 workers (60629 items) tests 9318 done 0 failed | 26 in flight, oldest 120s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................................... [432%]
...............................[contention-diag] +1450s soak 29p/233t rss 12.8G pss 11.9G swap 0.1G majflt 2428 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.7G, 1 descendant rss 0.0G pss 0.0G | host avail 26.1G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 2.71/0.89 io 2.87 cpu 14.28 | cgroup 12.6G/max oom_kill 0 | free scratch 299.2G/44922302i tmp 26.1G/985962i workspace 299.2G/44922302i | repeat-01 collected 26/26 workers (60629 items) tests 9391 done 0 failed | 26 in flight, oldest 136s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
......................................... [435%]
.......[contention-diag] +1466s soak 28p/231t rss 12.9G pss 11.9G swap 0.1G majflt 2870 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.7G | host avail 27.1G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 1.32/0.17 io 1.23 cpu 18.6 | cgroup 12.6G/max oom_kill 0 | free scratch 299.0G/44922125i tmp 26.1G/985962i workspace 299.0G/44922125i | repeat-01 collected 26/26 workers (60629 items) tests 9439 done 0 failed | 26 in flight, oldest 151s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.............................................................[contention-diag] +1481s soak 28p/227t rss 12.9G pss 11.9G swap 0.1G majflt 3017 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.7G | host avail 25.4G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.65/0.04 io 0.72 cpu 19.47 | cgroup 12.6G/max oom_kill 0 | free scratch 298.9G/44922069i tmp 26.1G/985988i workspace 298.9G/44922069i | repeat-01 collected 26/26 workers (60629 items) tests 9499 done 0 failed | 26 in flight, oldest 166s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.... [438%]
.........................................[contention-diag] +1496s soak 28p/223t rss 12.9G pss 11.9G swap 0.1G majflt 3125 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.7G | host avail 26.0G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.27/0.0 io 0.14 cpu 14.89 | cgroup 12.6G/max oom_kill 0 | free scratch 298.8G/44921998i tmp 26.1G/985990i workspace 298.8G/44921998i | scratch used 0.5G in 94199 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 9527 done 0 failed | 26 in flight, oldest 63s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................... [442%]
........................................................................ [445%]
....................................................................[contention-diag] +1514s soak 28p/207t rss 12.9G pss 11.9G swap 0.1G majflt 3167 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.7G | host avail 25.2G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 0.18 cpu 15.61 | cgroup 12.7G/max oom_kill 0 | free scratch 298.8G/44921380i tmp 26.1G/985990i workspace 298.8G/44921380i | repeat-01 collected 26/26 workers (60629 items) tests 9714 done 0 failed | 26 in flight, oldest 80s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.... [448%]
........................................................................ [452%]
........................................................................ [455%]
..........[contention-diag] +1529s soak 28p/216t rss 12.9G pss 11.9G swap 0.1G majflt 3234 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.7G | host avail 25.3G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.07/0.0 io 0.09 cpu 19.41 | cgroup 12.7G/max oom_kill 0 | free scratch 299.3G/44920929i tmp 26.1G/985990i workspace 299.3G/44920929i | repeat-01 collected 26/26 workers (60629 items) tests 9863 done 0 failed | 26 in flight, oldest 96s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................................[contention-diag] +1544s soak 29p/240t rss 12.9G pss 11.9G swap 0.1G majflt 3255 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 1 descendant rss 0.0G pss 0.0G | host avail 26.4G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.08 cpu 20.12 | cgroup 12.7G/max oom_kill 0 | free scratch 299.0G/44920638i tmp 26.1G/985963i workspace 299.0G/44920638i | repeat-01 collected 26/26 workers (60629 items) tests 9925 done 0 failed | 26 in flight, oldest 111s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........... [458%]
........................................................[contention-diag] +1560s soak 29p/219t rss 12.9G pss 11.9G swap 0.1G majflt 3261 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.7G, 1 descendant rss 0.0G pss 0.0G | host avail 24.1G/62.7G swapfree 52.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 18.73 | cgroup 12.7G/max oom_kill 0 | free scratch 298.9G/44920125i tmp 26.1G/985989i workspace 298.9G/44920125i | repeat-01 collected 26/26 workers (60629 items) tests 9991 done 0 failed | 26 in flight, oldest 126s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................ [462%]
........................[contention-diag] +1575s soak 28p/228t rss 12.9G pss 11.9G swap 0.1G majflt 3263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.7G | host avail 26.6G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.25/0.25 io 0.34 cpu 14.77 | cgroup 12.6G/max oom_kill 0 | free scratch 298.4G/44918400i tmp 26.1G/985989i workspace 298.4G/44918400i | repeat-01 collected 26/26 workers (60629 items) tests 10030 done 0 failed | 26 in flight, oldest 142s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................ [465%]
...................[contention-diag] +1590s soak 31p/244t rss 13.0G pss 12.0G swap 0.1G majflt 3271 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.8G, 3 descendant rss 0.1G pss 0.1G | host avail 25.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.19 cpu 21.71 | cgroup 12.7G/max oom_kill 0 | free scratch 298.3G/44918120i tmp 26.1G/985989i workspace 298.3G/44918120i | repeat-01 collected 26/26 workers (60629 items) tests 10089 done 0 failed | 26 in flight, oldest 157s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................................... [468%]
....................................................[contention-diag] +1606s soak 30p/234t rss 13.0G pss 12.0G swap 0.1G majflt 3342 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.8G, 2 descendant rss 0.1G pss 0.1G | host avail 23.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.23 cpu 21.15 | cgroup 12.5G/max oom_kill 0 | free scratch 298.2G/44917593i tmp 26.1G/985988i workspace 298.2G/44917593i | repeat-01 collected 26/26 workers (60629 items) tests 10203 done 0 failed | 26 in flight, oldest 172s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................... [472%]
........................................................................ [475%]
.....[contention-diag] +1621s soak 28p/223t rss 12.9G pss 12.0G swap 0.1G majflt 3350 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.8G | host avail 30.5G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 0.09 cpu 19.95 | cgroup 12.4G/max oom_kill 0 | free scratch 298.1G/44917317i tmp 26.1G/985988i workspace 298.1G/44917317i | scratch used 0.1G in 24268 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 10284 done 0 failed | 24 in flight, oldest 188s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................................................[contention-diag] +1638s soak 28p/224t rss 13.0G pss 12.0G swap 0.1G majflt 3367 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.8G | host avail 23.1G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.18/0.0 io 0.17 cpu 15.93 | cgroup 12.5G/max oom_kill 0 | free scratch 298.0G/44916569i tmp 26.1G/985988i workspace 298.0G/44916569i | repeat-01 collected 26/26 workers (60629 items) tests 10363 done 0 failed | 25 in flight, oldest 205s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
. [478%]
........................................................................ [482%]
........................................................................ [485%]
.........[contention-diag] +1654s soak 28p/229t rss 13.0G pss 11.9G swap 0.1G majflt 3924 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.8G | host avail 29.7G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 3.64/0.35 io 0.25 cpu 21.78 | cgroup 12.3G/max oom_kill 0 | free scratch 297.8G/44914949i tmp 26.1G/985988i workspace 297.8G/44914949i | repeat-01 collected 26/26 workers (60629 items) tests 10519 done 0 failed | 26 in flight, oldest 221s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................................................... [488%]
................[contention-diag] +1669s soak 30p/224t rss 13.0G pss 12.0G swap 0.1G majflt 4119 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.8G, 2 descendant rss 0.0G pss 0.0G | host avail 26.9G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 1.63/0.08 io 0.06 cpu 18.28 | cgroup 12.3G/max oom_kill 0 | free scratch 298.1G/44921802i tmp 26.1G/985988i workspace 298.1G/44921802i | repeat-01 collected 26/26 workers (60629 items) tests 10597 done 0 failed | 26 in flight, oldest 236s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................[contention-diag] +1685s soak 29p/224t rss 13.0G pss 12.0G swap 0.1G majflt 4206 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.8G, 1 descendant rss 0.0G pss 0.0G | host avail 25.8G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.42/0.01 io 0.01 cpu 11.41 | cgroup 12.4G/max oom_kill 0 | free scratch 298.0G/44921442i tmp 26.1G/985988i workspace 298.0G/44921442i | repeat-01 collected 26/26 workers (60629 items) tests 10627 done 0 failed | 26 in flight, oldest 251s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..........................[contention-diag] +1700s soak 28p/240t rss 13.0G pss 12.0G swap 0.1G majflt 4246 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.8G | host avail 26.7G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 0.0 cpu 16.81 | cgroup 12.3G/max oom_kill 0 | free scratch 297.4G/44920941i tmp 26.1G/985988i workspace 297.4G/44920941i | repeat-01 collected 26/26 workers (60629 items) tests 10653 done 0 failed | 26 in flight, oldest 267s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.. [492%]
............................................[contention-diag] +1716s soak 28p/234t rss 13.0G pss 12.0G swap 0.1G majflt 4290 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.8G | host avail 27.8G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.0 cpu 16.75 | cgroup 12.4G/max oom_kill 0 | free scratch 297.4G/44920570i tmp 26.1G/985988i workspace 297.4G/44920570i | repeat-01 collected 26/26 workers (60629 items) tests 10697 done 0 failed | 26 in flight, oldest 282s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................ [495%]
........................................................................ [498%]
....[contention-diag] +1731s soak 29p/230t rss 13.1G pss 12.0G swap 0.1G majflt 4389 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.8G, 1 descendant rss 0.0G pss 0.0G | host avail 31.0G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 0.0 cpu 23.35 | cgroup 12.4G/max oom_kill 0 | free scratch 296.9G/44919893i tmp 26.1G/985988i workspace 296.9G/44919893i | repeat-01 collected 26/26 workers (60629 items) tests 10797 done 0 failed | 26 in flight, oldest 298s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................................... [502%]
................................................[contention-diag] +1746s soak 28p/231t rss 13.0G pss 12.0G swap 0.1G majflt 4393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.8G | host avail 31.3G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.26 cpu 22.48 | cgroup 12.4G/max oom_kill 0 | free scratch 296.8G/44921798i tmp 26.1G/985988i workspace 296.8G/44921798i | scratch used 0.2G in 27274 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 10916 done 0 failed | 26 in flight, oldest 313s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........................ [505%]
........................................................................ [508%]
................................[contention-diag] +1764s soak 30p/244t rss 13.1G pss 12.0G swap 0.1G majflt 4417 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 2 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.2/0.09 io 1.07 cpu 22.84 | cgroup 12.5G/max oom_kill 0 | free scratch 296.9G/44921434i tmp 26.1G/985988i workspace 296.9G/44921434i | repeat-01 collected 26/26 workers (60629 items) tests 11044 done 0 failed | 26 in flight, oldest 48s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_plugins_pane_loads_and_groups
........................................ [512%]
........................[contention-diag] +1779s soak 31p/250t rss 13.1G pss 12.0G swap 0.1G majflt 4454 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.8G, 3 descendant rss 0.0G pss 0.0G | host avail 32.1G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 1.33 cpu 25.74 | cgroup 12.5G/max oom_kill 0 | free scratch 296.9G/44920980i tmp 26.1G/985988i workspace 296.9G/44920980i | repeat-01 collected 26/26 workers (60629 items) tests 11110 done 0 failed | 26 in flight, oldest 51s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
................................................ [515%]
........................................................................ [518%]
.........................[contention-diag] +1795s soak 31p/235t rss 13.2G pss 12.1G swap 0.1G majflt 4587 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 3 descendant rss 0.1G pss 0.0G | host avail 30.2G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.31 cpu 21.27 | cgroup 12.6G/max oom_kill 0 | free scratch 296.9G/44920552i tmp 26.1G/985988i workspace 296.9G/44920552i | repeat-01 collected 26/26 workers (60629 items) tests 11250 done 0 failed | 26 in flight, oldest 67s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
............................................... [522%]
........................................................................ [525%]
...............................................[contention-diag] +1810s soak 31p/227t rss 13.2G pss 12.1G swap 0.1G majflt 4821 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 3 descendant rss 0.1G pss 0.1G | host avail 25.1G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 0.07 cpu 20.11 | cgroup 12.6G/max oom_kill 0 | free scratch 297.4G/44920068i tmp 26.1G/985988i workspace 297.4G/44920068i | repeat-01 collected 26/26 workers (60629 items) tests 11421 done 0 failed | 26 in flight, oldest 82s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
......................... [528%]
.....[contention-diag] +1825s soak 30p/220t rss 13.1G pss 12.1G swap 0.1G majflt 4707 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 2 descendant rss 0.0G pss 0.0G | host avail 26.8G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.21/0.0 io 0.19 cpu 21.08 | cgroup 12.6G/max oom_kill 0 | free scratch 297.2G/44919926i tmp 26.1G/985988i workspace 297.2G/44919926i | repeat-01 collected 26/26 workers (60629 items) tests 11452 done 0 failed | 26 in flight, oldest 49s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_preview_back_retains_sparse_draft_and_running_primary_restarts
...............................................................[contention-diag] +1841s soak 31p/228t rss 13.2G pss 12.1G swap 0.1G majflt 4721 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 3 descendant rss 0.1G pss 0.0G | host avail 25.1G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.0 io 0.03 cpu 23.7 | cgroup 12.6G/max oom_kill 0 | free scratch 297.1G/44919626i tmp 26.1G/985987i workspace 297.1G/44919626i | repeat-01 collected 26/26 workers (60629 items) tests 11514 done 0 failed | 26 in flight, oldest 61s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
.... [532%]
........................................................................ [535%]
...[contention-diag] +1856s soak 29p/215t rss 13.2G pss 12.1G swap 0.1G majflt 4744 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 1 descendant rss 0.0G pss 0.0G | host avail 22.5G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.29/0.0 io 0.15 cpu 17.71 | cgroup 12.6G/max oom_kill 0 | free scratch 296.8G/44918940i tmp 26.1G/985987i workspace 296.8G/44918940i | repeat-01 collected 26/26 workers (60629 items) tests 11588 done 0 failed | 26 in flight, oldest 57s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_loads_and_populates_tree
..................................................................... [538%]
........................................[contention-diag] +1871s soak 30p/228t rss 13.2G pss 12.1G swap 0.1G majflt 4756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 2 descendant rss 0.1G pss 0.0G | host avail 21.3G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 0.03 cpu 17.25 | cgroup 12.7G/max oom_kill 0 | free scratch 296.7G/44918420i tmp 26.1G/985987i workspace 296.7G/44918420i | scratch used 0.3G in 48016 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 11701 done 0 failed | 26 in flight, oldest 43s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
................................ [542%]
........................................................................ [545%]
.............[contention-diag] +1889s soak 29p/229t rss 13.2G pss 12.1G swap 0.1G majflt 4783 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 1 descendant rss 0.0G pss 0.0G | host avail 25.2G/62.7G swapfree 50.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 19.8 | cgroup 12.7G/max oom_kill 0 | free scratch 296.5G/44917930i tmp 26.1G/985987i workspace 296.5G/44917930i | repeat-01 collected 26/26 workers (60629 items) tests 11820 done 0 failed | 26 in flight, oldest 60s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
.................................................[contention-diag] +1904s soak 30p/226t rss 13.2G pss 12.2G swap 0.1G majflt 4790 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 2 descendant rss 0.1G pss 0.1G | host avail 24.4G/62.7G swapfree 50.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 21.64 | cgroup 12.8G/max oom_kill 0 | free scratch 296.3G/44917768i tmp 26.1G/985987i workspace 296.3G/44917768i | repeat-01 collected 26/26 workers (60629 items) tests 11868 done 0 failed | 26 in flight, oldest 76s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
.......... [548%]
...................................................................[contention-diag] +1920s soak 29p/219t rss 13.2G pss 12.1G swap 0.1G majflt 4796 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.9G, 1 descendant rss 0.0G pss 0.0G | host avail 24.9G/62.7G swapfree 50.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 13.99 | cgroup 12.7G/max oom_kill 0 | free scratch 295.8G/44916409i tmp 26.1G/985986i workspace 295.8G/44916409i | repeat-01 collected 26/26 workers (60629 items) tests 11940 done 0 failed | 26 in flight, oldest 91s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
..... [552%]
.....................................................................[contention-diag] +1935s soak 29p/222t rss 13.2G pss 12.1G swap 0.1G majflt 4807 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.9G, 1 descendant rss 0.0G pss 0.0G | host avail 29.8G/62.7G swapfree 50.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.33 cpu 15.38 | cgroup 12.7G/max oom_kill 0 | free scratch 296.4G/44915592i tmp 26.1G/985986i workspace 296.4G/44915592i | repeat-01 collected 26/26 workers (60629 items) tests 12018 done 0 failed | 26 in flight, oldest 51s gw9 tests/ace/tui/test_projects_pane.py::test_projects_session_round_trips_current_project_display
... [555%]
............................................................[contention-diag] +1950s soak 29p/230t rss 13.2G pss 12.1G swap 0.1G majflt 4817 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.9G, 1 descendant rss 0.0G pss 0.0G | host avail 27.1G/62.7G swapfree 50.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 16.56 | cgroup 12.8G/max oom_kill 0 | free scratch 296.4G/44915350i tmp 26.1G/985984i workspace 296.4G/44915350i | repeat-01 collected 26/26 workers (60629 items) tests 12080 done 0 failed | 26 in flight, oldest 61s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
............ [558%]
.............................................[contention-diag] +1966s soak 29p/206t rss 13.2G pss 12.1G swap 0.1G majflt 4820 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.9G, 1 descendant rss 0.0G pss 0.0G | host avail 25.1G/62.7G swapfree 50.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 17.47 | cgroup 12.7G/max oom_kill 0 | free scratch 296.4G/44915066i tmp 26.1G/985983i workspace 296.4G/44915066i | repeat-01 collected 26/26 workers (60629 items) tests 12127 done 0 failed | 26 in flight, oldest 53s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_filter_narrows_tree
........................... [562%]
...........................................[contention-diag] +1981s soak 30p/233t rss 13.3G pss 12.2G swap 0.1G majflt 4821 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.9G, 2 descendant rss 0.1G pss 0.1G | host avail 23.5G/62.7G swapfree 50.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 17.82 | cgroup 12.8G/max oom_kill 0 | free scratch 296.3G/44914909i tmp 26.1G/985982i workspace 296.3G/44914909i | repeat-01 collected 26/26 workers (60629 items) tests 12209 done 0 failed | 26 in flight, oldest 48s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_all_skipped_toasts_reasons_and_cleans_up
............................. [565%]
........................................................................ [568%]
.....................................................................[contention-diag] +1996s soak 29p/223t rss 13.2G pss 12.1G swap 0.1G majflt 4827 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 12.0G, 1 descendant rss 0.0G pss 0.0G | host avail 22.1G/62.7G swapfree 50.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 15.68 | cgroup 12.8G/max oom_kill 0 | free scratch 296.3G/44914214i tmp 26.1G/985980i workspace 296.3G/44914214i | scratch used 0.4G in 66094 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 12356 done 0 failed | 26 in flight, oldest 46s gw24 tests/ace/tui/test_projects_pane_init_flow_collision.py::test_second_activation_uses_real_collision_path
... [572%]
........................................................................ [575%]
...............................................[contention-diag] +2014s soak 29p/216t rss 13.1G pss 12.0G swap 0.2G majflt 4845 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.9G, 1 descendant rss 0.0G pss 0.0G | host avail 21.8G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 13.01 | cgroup 12.7G/max oom_kill 0 | free scratch 295.8G/44913572i tmp 26.1G/985979i workspace 295.8G/44913572i | repeat-01 collected 26/26 workers (60629 items) tests 12499 done 0 failed | 26 in flight, oldest 62s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
......................... [578%]
........................................................................ [581%]
..................................................................[contention-diag] +2029s soak 31p/232t rss 13.2G pss 12.1G swap 0.2G majflt 4989 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.9G, 3 descendant rss 0.0G pss 0.0G | host avail 27.9G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.79 cpu 14.15 | cgroup 12.8G/max oom_kill 0 | free scratch 295.4G/44913311i tmp 26.1G/985979i workspace 295.4G/44913311i | repeat-01 collected 26/26 workers (60629 items) tests 12664 done 0 failed | 26 in flight, oldest 78s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
...... [585%]
........................................................................ [588%]
........................................................[contention-diag] +2044s soak 29p/225t rss 13.2G pss 12.1G swap 0.2G majflt 5005 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 12.0G, 1 descendant rss 0.0G pss 0.0G | host avail 28.9G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.61 cpu 15.54 | cgroup 12.8G/max oom_kill 0 | free scratch 294.3G/44912782i tmp 26.1G/985979i workspace 294.3G/44912782i | repeat-01 collected 26/26 workers (60629 items) tests 12788 done 0 failed | 26 in flight, oldest 93s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
................ [591%]
..................................F[contention-failure] call tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f705663eba0>

    async def test_group_cycle_is_view_sensitive_and_projects_reuses_result(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        calls: list[tuple[StatisticsView, StatsRange, str | None, str | None]] = []
        _patch_center(monkeypatch, calls)
    
        async with AcePage() as page:
            _, pane = await _open_statistics(page)
    
            grouping_views = {"projects", "macros", "perf", "footprint"}
            for view in VIEW_ORDER:
                pane._set_view(view)
                await page.pause()
                group_scope = pane.query_one("#statistics-scope-group", Static)
                assert group_scope.display is (view in grouping_views)
                if view in grouping_views:
                    continue
                pane.action_cycle_group()
                await page.pause()
                assert pane._projects_group_by == "project"
                assert pane._perf_group_by == "subsystem"
    
            pane._set_view("perf")
            await page.wait_for(
                lambda _state: (
                    pane._last_result is not None
                    and pane._last_result.perf is not None
                    and not pane._loading
                    and (
                        pane._load_debouncer is None or not pane._load_debouncer.is_pending
                    )
                )
            )
            pane._set_view("projects")
            await _wait_statistics_settled(page, pane)
            cached_calls = len(calls)
            pane.action_cycle_group()
            await page.pause()
    
            assert pane._projects_group_by == "repo"
            assert len(calls) == cached_calls
            assert "Projects · By Repo" in _scope_plain(pane, "group")
            assert "group" not in (
                pane.query_one("#statistics-hints", Static).render().plain
            )
    
            pane._set_view("macros")
            await _wait_statistics_settled(page, pane)
            cached_calls = len(calls)
            pane.action_cycle_group()
            await page.pause()
            assert pane._macros_group_by == "model"
            assert len(calls) == cached_calls
            assert "Macros · By Model" in _scope_plain(pane, "group")
    
            pane._set_view("providers")
            await _wait_statistics_settled(page, pane)
            cached_calls = len(calls)
            pane.action_cycle_group()
            await page.pause()
            assert pane._projects_group_by == "repo"
            assert pane._macros_group_by == "model"
            assert pane._perf_group_by == "subsystem"
            assert len(calls) == cached_calls
            assert pane.query_one("#statistics-scope-group", Static).display is False
    
            pane._set_view("projects")
>           await _wait_statistics_settled(page, pane)

tests/ace/tui/test_statistics_pane_filters.py:192: 
_ _ _ _ _ _ _ _ _
..................................... [595%]
........................................................................ [598%]
......................[contention-diag] +2060s soak 29p/226t rss 13.2G pss 12.1G swap 0.2G majflt 5245 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 12.0G, 1 descendant rss 0.0G pss 0.0G | host avail 29.7G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.99 cpu 12.43 | cgroup 12.8G/max oom_kill 0 | free scratch 294.3G/44899074i tmp 26.1G/985979i workspace 294.3G/44899076i | repeat-01 collected 26/26 workers (60629 items) tests 12968 done 1 failed | 26 in flight, oldest 62s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
.................................................. [601%]
........................................................................ [605%]
.........[contention-diag] +2076s soak 30p/228t rss 13.8G pss 12.2G swap 0.2G majflt 5268 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 12.0G, 2 descendant rss 0.6G pss 0.1G | host avail 24.2G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.32/0.32 io 11.55 cpu 11.39 | cgroup 12.8G/max oom_kill 0 | free scratch 293.8G/44885931i tmp 26.1G/985600i workspace 293.8G/44885931i | repeat-01 collected 26/26 workers (60629 items) tests 13107 done 1 failed | 26 in flight, oldest 78s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
............................................................... [608%]
.......................[contention-diag] +2091s soak 29p/218t rss 13.2G pss 12.1G swap 0.2G majflt 5293 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 12.0G, 1 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.15/0.11 io 4.73 cpu 14.97 | cgroup 12.8G/max oom_kill 0 | free scratch 294.0G/44882640i tmp 26.1G/985925i workspace 294.0G/44882640i | repeat-01 collected 26/26 workers (60629 items) tests 13194 done 1 failed | 25 in flight, oldest 56s gw11 tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_hint_line_switches_to_jump_variant
................................................. [611%]
........................................................................ [615%]
.........................................................[contention-diag] +2106s soak 30p/229t rss 13.2G pss 12.1G swap 0.2G majflt 5318 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 12.0G, 2 descendant rss 0.0G pss 0.0G | host avail 28.7G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 1.68 cpu 15.3 | cgroup 12.8G/max oom_kill 0 | free scratch 294.0G/44882326i tmp 26.1G/985925i workspace 294.0G/44882326i | repeat-01 collected 26/26 workers (60629 items) tests 13374 done 1 failed | 25 in flight, oldest 53s gw12 tests/ace/tui/test_plugins_browser_pane_marks.py::test_mark_all_installable_clis_then_unmarks
............... [618%]
........................................................................ [621%]
........................................................................ [625%]
[contention-diag] +2122s soak 30p/226t rss 13.2G pss 12.1G swap 0.2G majflt 5351 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 12.0G, 2 descendant rss 0.0G pss 0.0G | host avail 28.8G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.55 cpu 16.99 | cgroup 12.8G/max oom_kill 0 | free scratch 294.0G/44881707i tmp 26.1G/985925i workspace 294.0G/44881707i | scratch used 0.4G in 76171 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 13509 done 1 failed | 26 in flight, oldest 53s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_close_each_of_three_panels_keeps_textual_focus
........................................................................ [628%]
....................[contention-diag] +2139s soak 29p/227t rss 13.3G pss 12.2G swap 0.2G majflt 5416 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.1G pss 12.0G, 1 descendant rss 0.1G pss 0.0G | host avail 26.6G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.85 cpu 16.94 | cgroup 12.9G/max oom_kill 0 | free scratch 294.0G/44881589i tmp 26.1G/985953i workspace 294.0G/44881589i | repeat-01 collected 26/26 workers (60629 items) tests 13624 done 1 failed | 25 in flight, oldest 71s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_close_each_of_three_panels_keeps_textual_focus
.................................................... [631%]
.................................[contention-diag] +2154s soak 31p/238t rss 13.4G pss 12.3G swap 0.2G majflt 5422 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.1G pss 12.0G, 3 descendant rss 0.2G pss 0.1G | host avail 27.5G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.54 cpu 17.82 | cgroup 13.1G/max oom_kill 0 | free scratch 293.5G/44881282i tmp 26.1G/985953i workspace 293.5G/44881282i | repeat-01 collected 26/26 workers (60629 items) tests 13710 done 1 failed | 26 in flight, oldest 75s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs0-#git:foo ]
....................................... [635%]
.............[contention-diag] +2170s soak 33p/225t rss 13.2G pss 12.0G swap 0.6G majflt 5904 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.9G pss 11.7G, 5 descendant rss 0.2G pss 0.2G | host avail 23.1G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 6.04/4.84 io 3.65 cpu 14.2 | cgroup 12.7G/max oom_kill 0 | free scratch 292.9G/44880552i tmp 26.1G/985952i workspace 292.9G/44880552i | repeat-01 collected 26/26 workers (60629 items) tests 13765 done 1 failed | 26 in flight, oldest 79s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_live_tick_keeps_ctrl_j_card
........................................................... [638%]
.................................[contention-diag] +2186s soak 30p/226t rss 13.1G pss 11.8G swap 0.6G majflt 7053 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.9G pss 11.7G, 2 descendant rss 0.1G pss 0.0G | host avail 22.5G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 2.57/1.06 io 0.73 cpu 17.77 | cgroup 12.6G/max oom_kill 0 | free scratch 292.7G/44880034i tmp 26.1G/985952i workspace 292.7G/44880034i | repeat-01 collected 26/26 workers (60629 items) tests 13854 done 1 failed | 25 in flight, oldest 74s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
....................................... [641%]
............[contention-diag] +2202s soak 32p/246t rss 13.1G pss 11.8G swap 0.6G majflt 8334 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.9G pss 11.7G, 4 descendant rss 0.0G pss 0.0G | host avail 23.0G/62.7G swapfree 47.5G/64.0G oom_kill +0 | psi10 mem 2.84/0.31 io 1.76 cpu 14.39 | cgroup 12.7G/max oom_kill 0 | free scratch 292.3G/44879694i tmp 26.1G/985952i workspace 292.3G/44879694i | repeat-01 collected 26/26 workers (60629 items) tests 13906 done 1 failed | 26 in flight, oldest 90s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............................................................ [645%]
..............[contention-diag] +2217s soak 29p/220t rss 13.1G pss 11.8G swap 0.6G majflt 8688 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.9G pss 11.7G, 1 descendant rss 0.0G pss 0.0G | host avail 23.5G/62.7G swapfree 47.5G/64.0G oom_kill +0 | psi10 mem 2.11/0.07 io 0.5 cpu 17.57 | cgroup 12.9G/max oom_kill 0 | free scratch 292.1G/44879266i tmp 26.1G/985952i workspace 292.1G/44879266i | repeat-01 collected 26/26 workers (60629 items) tests 13975 done 1 failed | 26 in flight, oldest 105s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.......................................................... [648%]
........................................................................ [651%]
..............................[contention-diag] +2232s soak 31p/218t rss 13.0G pss 11.8G swap 0.7G majflt 8989 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.9G pss 11.6G, 3 descendant rss 0.0G pss 0.0G | host avail 19.6G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.54/0.08 io 0.59 cpu 14.91 | cgroup 12.5G/max oom_kill 0 | free scratch 291.9G/44878622i tmp 26.1G/985952i workspace 291.9G/44878622i | repeat-01 collected 26/26 workers (60629 items) tests 14135 done 1 failed | 26 in flight, oldest 120s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.......................................... [655%]
........................................................................ [658%]
........................................................................ [661%]
.................................[contention-diag] +2248s soak 28p/213t rss 13.0G pss 11.7G swap 0.7G majflt 9131 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.9G pss 11.7G | host avail 22.7G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.1/0.01 io 0.88 cpu 14.48 | cgroup 12.5G/max oom_kill 0 | free scratch 291.6G/44877810i tmp 26.1G/985951i workspace 291.6G/44877810i | scratch used 0.2G in 42063 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 14302 done 1 failed | 26 in flight, oldest 64s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
....................................... [665%]
...................................................................[contention-diag] +2265s soak 28p/221t rss 13.0G pss 11.8G swap 0.7G majflt 9520 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.9G pss 11.7G | host avail 22.4G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.55 cpu 17.03 | cgroup 12.6G/max oom_kill 0 | free scratch 291.3G/44876719i tmp 26.1G/985949i workspace 291.3G/44876719i | repeat-01 collected 26/26 workers (60629 items) tests 14463 done 1 failed | 25 in flight, oldest 82s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
..... [668%]
........................................................................ [671%]
..........................................................[contention-diag] +2280s soak 30p/232t rss 13.1G pss 11.8G swap 0.7G majflt 9833 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.9G pss 11.7G, 2 descendant rss 0.0G pss 0.0G | host avail 23.8G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.35 cpu 15.41 | cgroup 12.6G/max oom_kill 0 | free scratch 291.2G/44875804i tmp 26.1G/985950i workspace 291.2G/44875804i | repeat-01 collected 26/26 workers (60629 items) tests 14600 done 1 failed | 26 in flight, oldest 51s gw23 tests/ace/tui/test_link_follow_planner.py::test_missing_bead_hydrates_then_reveals
.............. [675%]
........................................................................ [678%]
.......................................................................[contention-diag] +2296s soak 33p/224t rss 13.1G pss 11.8G swap 0.7G majflt 10045 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.7G, 5 descendant rss 0.1G pss 0.0G | host avail 34.3G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 18.27 | cgroup 12.6G/max oom_kill 0 | free scratch 290.9G/44875474i tmp 26.1G/985950i workspace 290.9G/44875474i | repeat-01 collected 26/26 workers (60629 items) tests 14740 done 1 failed | 26 in flight, oldest 66s gw23 tests/ace/tui/test_link_follow_planner.py::test_missing_bead_hydrates_then_reveals
. [681%]
........................................................................ [685%]
.....................................................................[contention-diag] +2311s soak 33p/234t rss 13.3G pss 12.0G swap 0.7G majflt 10150 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.8G, 5 descendant rss 0.2G pss 0.1G | host avail 32.6G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.4 cpu 16.5 | cgroup 12.7G/max oom_kill 0 | free scratch 290.9G/44874742i tmp 26.1G/985950i workspace 290.9G/44874742i | repeat-01 collected 26/26 workers (60629 items) tests 14900 done 1 failed | 26 in flight, oldest 71s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
... [688%]
........................................................................ [691%]
........................................................................ [695%]
........................................................................ [698%]
.........[contention-diag] +2326s soak 32p/211t rss 13.2G pss 11.9G swap 0.7G majflt 10515 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.8G, 4 descendant rss 0.1G pss 0.1G | host avail 32.1G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.54 cpu 19.22 | cgroup 12.7G/max oom_kill 0 | free scratch 290.9G/44873268i tmp 26.1G/985950i workspace 290.9G/44873268i | repeat-01 collected 26/26 workers (60629 items) tests 15124 done 1 failed | 26 in flight, oldest 63s gw2 tests/ace/tui/test_startup_stopwatch_live_update.py::test_slow_mount_state_read_does_not_block_app_key_dispatch
............................................................... [701%]
..............................................[contention-diag] +2342s soak 35p/237t rss 13.3G pss 11.9G swap 0.7G majflt 10879 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.8G, 7 descendant rss 0.1G pss 0.1G | host avail 32.7G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 1.47 cpu 19.71 | cgroup 12.7G/max oom_kill 0 | free scratch 290.9G/44872252i tmp 26.1G/985950i workspace 290.9G/44872252i | repeat-01 collected 26/26 workers (60629 items) tests 15235 done 1 failed | 26 in flight, oldest 79s gw2 tests/ace/tui/test_startup_stopwatch_live_update.py::test_slow_mount_state_read_does_not_block_app_key_dispatch
.......................... [705%]
........................................................................ [708%]
...........................................................[contention-diag] +2357s soak 30p/241t rss 13.2G pss 11.9G swap 0.7G majflt 11028 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.1G pss 11.8G, 2 descendant rss 0.0G pss 0.0G | host avail 32.7G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.96 cpu 19.56 | cgroup 12.7G/max oom_kill 0 | free scratch 290.9G/44871310i tmp 26.1G/985949i workspace 290.9G/44871310i | repeat-01 collected 26/26 workers (60629 items) tests 15390 done 1 failed | 26 in flight, oldest 88s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
............. [711%]
........................................................................ [715%]
........................................................................ [718%]
........................................................................ [721%]
............................................................[contention-diag] +2372s soak 32p/225t rss 13.3G pss 11.9G swap 0.7G majflt 11132 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.1G pss 11.8G, 4 descendant rss 0.1G pss 0.0G | host avail 31.4G/62.7G swapfree 47.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.03 cpu 17.15 | cgroup 12.8G/max oom_kill 0 | free scratch 291.3G/44870053i tmp 26.1G/985948i workspace 291.3G/44870053i | scratch used 0.3G in 60195 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 15639 done 1 failed | 25 in flight, oldest 66s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............ [724%]
........................................................................ [728%]
.......................................................[contention-diag] +2390s soak 33p/213t rss 13.3G pss 12.0G swap 0.7G majflt 11184 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.1G pss 11.9G, 5 descendant rss 0.1G pss 0.0G | host avail 29.3G/62.7G swapfree 47.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 15.3 | cgroup 13.0G/max oom_kill 0 | free scratch 291.3G/44869101i tmp 26.1G/985946i workspace 291.3G/44869101i | repeat-01 collected 26/26 workers (60629 items) tests 15821 done 1 failed | 26 in flight, oldest 83s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................. [731%]
........................................................................ [734%]
....................................................[contention-diag] +2405s soak 33p/206t rss 13.5G pss 12.1G swap 0.6G majflt 11306 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.1G pss 11.9G, 5 descendant rss 0.2G pss 0.2G | host avail 30.0G/62.7G swapfree 47.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.42 cpu 16.58 | cgroup 13.0G/max oom_kill 0 | free scratch 291.2G/44868543i tmp 26.1G/985948i workspace 291.2G/44868543i | repeat-01 collected 26/26 workers (60629 items) tests 15959 done 1 failed | 26 in flight, oldest 99s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................... [738%]
........................................................................ [741%]
........................................................................ [744%]
...............[contention-diag] +2421s soak 30p/223t rss 13.3G pss 12.0G swap 0.6G majflt 11375 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.1G pss 11.9G, 2 descendant rss 0.1G pss 0.0G | host avail 27.1G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.62 cpu 15.96 | cgroup 12.9G/max oom_kill 0 | free scratch 291.2G/44867676i tmp 26.1G/985948i workspace 291.2G/44867676i | repeat-01 collected 26/26 workers (60629 items) tests 16139 done 1 failed | 26 in flight, oldest 114s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
......................................................... [748%]
........................................................................ [751%]
........................................................................ [754%]
.....................................[contention-diag] +2436s soak 34p/223t rss 13.4G pss 12.1G swap 0.6G majflt 11414 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.2G pss 11.9G, 6 descendant rss 0.1G pss 0.1G | host avail 29.1G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 15.83 | cgroup 13.0G/max oom_kill 0 | free scratch 291.3G/44866856i tmp 26.1G/985948i workspace 291.3G/44866856i | repeat-01 collected 26/26 workers (60629 items) tests 16361 done 1 failed | 26 in flight, oldest 129s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................... [758%]
........................................................................ [761%]
........................................................................ [764%]
.............................................................[contention-diag] +2451s soak 33p/235t rss 13.4G pss 12.1G swap 0.6G majflt 11890 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.2G pss 11.9G, 5 descendant rss 0.1G pss 0.1G | host avail 32.3G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.27 cpu 18.09 | cgroup 13.0G/max oom_kill 0 | free scratch 291.3G/44865941i tmp 26.1G/985948i workspace 291.3G/44865940i | repeat-01 collected 26/26 workers (60629 items) tests 16619 done 1 failed | 26 in flight, oldest 145s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........... [768%]
........................................................................ [771%]
........................................................................ [774%]
..................................................[contention-diag] +2467s soak 37p/229t rss 13.6G pss 12.2G swap 0.6G majflt 12034 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.2G pss 11.9G, 9 descendant rss 0.3G pss 0.2G | host avail 30.3G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.41 cpu 18.35 | cgroup 13.4G/max oom_kill 0 | free scratch 291.0G/44854587i tmp 26.1G/985947i workspace 291.0G/44854587i | repeat-01 collected 26/26 workers (60629 items) tests 16813 done 1 failed | 26 in flight, oldest 160s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
...................... [778%]
........................................................................ [781%]
........................................................................ [784%]
........................................................................ [788%]
[contention-diag] +2482s soak 32p/222t rss 13.4G pss 12.1G swap 0.6G majflt 12068 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.2G pss 11.9G, 4 descendant rss 0.0G pss 0.0G | host avail 30.3G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 15.14 | cgroup 13.2G/max oom_kill 0 | free scratch 291.0G/44856362i tmp 26.1G/985947i workspace 291.0G/44856362i | repeat-01 collected 26/26 workers (60629 items) tests 17058 done 1 failed | 25 in flight, oldest 166s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
........................................................................ [791%]
........................................................................ [794%]
..........................................................[contention-diag] +2498s soak 33p/196t rss 13.5G pss 12.1G swap 0.6G majflt 12121 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.2G pss 12.0G, 5 descendant rss 0.1G pss 0.0G | host avail 30.5G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 15.92 | cgroup 13.1G/max oom_kill 0 | free scratch 291.0G/44855320i tmp 26.1G/985947i workspace 291.0G/44855320i | scratch used 0.5G in 86731 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 17245 done 1 failed | 26 in flight, oldest 122s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
.............. [798%]
........................................................................ [801%]
......................................................................[contention-diag] +2515s soak 35p/218t rss 13.5G pss 12.1G swap 0.6G majflt 12292 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.3G pss 12.0G, 7 descendant rss 0.1G pss 0.1G | host avail 28.4G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 19.24 | cgroup 13.1G/max oom_kill 0 | free scratch 291.0G/44854917i tmp 26.1G/985947i workspace 291.0G/44854917i | repeat-01 collected 26/26 workers (60629 items) tests 17420 done 1 failed | 26 in flight, oldest 54s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_plugins_pane_error_state
.. [804%]
........................................................................ [808%]
........................................................................ [811%]
......[contention-diag] +2530s soak 34p/225t rss 13.5G pss 12.1G swap 0.6G majflt 12363 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.3G pss 12.0G, 6 descendant rss 0.1G pss 0.0G | host avail 30.4G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 0.27 cpu 18.21 | cgroup 13.1G/max oom_kill 0 | free scratch 290.7G/44854499i tmp 26.1G/985947i workspace 290.7G/44854499i | repeat-01 collected 26/26 workers (60629 items) tests 17569 done 1 failed | 26 in flight, oldest 63s gw23 tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui
.................................................................. [814%]
.........................................................[contention-diag] +2546s soak 33p/209t rss 13.6G pss 12.2G swap 0.6G majflt 12453 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.3G pss 12.0G, 5 descendant rss 0.2G pss 0.1G | host avail 33.0G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.6 cpu 20.89 | cgroup 13.3G/max oom_kill 0 | free scratch 290.6G/44854242i tmp 26.1G/985947i workspace 290.6G/44854242i | repeat-01 collected 26/26 workers (60629 items) tests 17694 done 1 failed | 26 in flight, oldest 71s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_rapid_space_escape_falls_back_without_collision
............... [818%]
........................................................................ [821%]
........................................................................ [824%]
........................................................................ [828%]
.....................................................[contention-diag] +2561s soak 31p/194t rss 13.4G pss 12.1G swap 0.6G majflt 12515 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.3G pss 12.0G, 3 descendant rss 0.0G pss 0.0G | host avail 32.9G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.48 cpu 21.08 | cgroup 13.2G/max oom_kill 0 | free scratch 290.6G/44853656i tmp 26.1G/985946i workspace 290.6G/44853656i | repeat-01 collected 26/26 workers (60629 items) tests 17980 done 1 failed | 26 in flight, oldest 55s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
................... [831%]
........................................................................ [834%]
........................................................................ [838%]
........................................................................ [841%]
........................................................................ [844%]
...................[contention-diag] +2576s soak 30p/205t rss 13.5G pss 12.1G swap 0.6G majflt 12722 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.3G pss 12.0G, 2 descendant rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 19.38 | cgroup 13.1G/max oom_kill 0 | free scratch 290.6G/44852695i tmp 26.1G/985945i workspace 290.6G/44852695i | repeat-01 collected 26/26 workers (60629 items) tests 18296 done 1 failed | 25 in flight, oldest 71s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
..................................................... [848%]
........................................................................ [851%]
.......................................................................[contention-diag] +2592s soak 36p/214t rss 13.6G pss 12.2G swap 0.5G majflt 22198 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.0G, 8 descendant rss 0.0G pss 0.0G | host avail 29.5G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 15.66 | cgroup 13.3G/max oom_kill 0 | free scratch 290.6G/44851927i tmp 26.1G/985945i workspace 290.6G/44851927i | repeat-01 collected 26/26 workers (60629 items) tests 18385 done 1 failed | 25 in flight, oldest 86s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
. [854%]
........................................................................ [858%]
........................................................................ [861%]
....................................................................[contention-diag] +2607s soak 31p/204t rss 13.6G pss 12.2G swap 0.5G majflt 22494 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.0G, 3 descendant rss 0.0G pss 0.0G | host avail 32.1G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 16.66 | cgroup 13.3G/max oom_kill 0 | free scratch 290.4G/44851005i tmp 26.1G/985945i workspace 290.4G/44851005i | repeat-01 collected 26/26 workers (60629 items) tests 18709 done 1 failed | 26 in flight, oldest 64s gw22 tests/ace/tui/test_statistics_pane_current_project_seed.py::test_cycle_can_escape_a_seeded_project_filter
.... [864%]
........................................................................ [867%]
........................................................................ [871%]
..........................................................[contention-diag] +2623s soak 32p/200t rss 13.6G pss 12.2G swap 0.5G majflt 22597 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.0G, 4 descendant rss 0.0G pss 0.0G | host avail 31.1G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.14 cpu 17.53 | cgroup 13.3G/max oom_kill 0 | free scratch 291.0G/44850081i tmp 26.1G/985943i workspace 291.0G/44850081i | scratch used 0.5G in 97520 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 18902 done 1 failed | 26 in flight, oldest 70s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
.............. [874%]
........................................................................ [877%]
........................................................................ [881%]
........................................................................ [884%]
.....................................................[contention-diag] +2640s soak 33p/198t rss 13.6G pss 12.3G swap 0.5G majflt 22627 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 5 descendant rss 0.0G pss 0.0G | host avail 30.9G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.56 cpu 18.76 | cgroup 13.4G/max oom_kill 0 | free scratch 291.0G/44849733i tmp 26.1G/985943i workspace 291.0G/44849733i | repeat-01 collected 26/26 workers (60629 items) tests 19201 done 1 failed | 26 in flight, oldest 59s gw16 tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_not_installed_toasts
................... [887%]
........................................................................ [891%]
........................................................................ [894%]
........................................................................ [897%]
.............................................................[contention-diag] +2655s soak 32p/212t rss 13.7G pss 12.3G swap 0.5G majflt 22781 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 4 descendant rss 0.1G pss 0.0G | host avail 28.6G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.5 cpu 17.43 | cgroup 13.5G/max oom_kill 0 | free scratch 291.0G/44848610i tmp 26.1G/985941i workspace 291.0G/44848610i | repeat-01 collected 26/26 workers (60629 items) tests 19499 done 1 failed | 26 in flight, oldest 57s gw9 tests/ace/tui/test_projects_pane.py::test_configured_cycle_subtab_keys_bubble_and_forward
........... [901%]
.............s.......................................ss................. [904%]
.......................................................[contention-diag] +2671s soak 34p/201t rss 13.7G pss 12.3G swap 0.5G majflt 22869 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 6 descendant rss 0.1G pss 0.0G | host avail 27.0G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.51 cpu 13.79 | cgroup 13.5G/max oom_kill 0 | free scratch 291.1G/44849039i tmp 26.1G/985941i workspace 291.1G/44849039i | repeat-01 collected 26/26 workers (60629 items) tests 19627 done 1 failed | 26 in flight, oldest 66s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
................. [907%]
........................................................................ [911%]
........................................................................ [914%]
........................................................................ [917%]
........................................................................ [921%]
......................................[contention-diag] +2687s soak 32p/210t rss 13.7G pss 12.3G swap 0.5G majflt 22964 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 4 descendant rss 0.1G pss 0.0G | host avail 27.1G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.38 cpu 13.85 | cgroup 13.4G/max oom_kill 0 | free scratch 290.9G/44847682i tmp 26.1G/985941i workspace 290.9G/44847682i | repeat-01 collected 26/26 workers (60629 items) tests 19970 done 1 failed | 26 in flight, oldest 82s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.................................. [924%]
........................................................................ [927%]
......[contention-diag] +2702s soak 35p/219t rss 13.8G pss 12.3G swap 0.5G majflt 22994 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 7 descendant rss 0.1G pss 0.1G | host avail 27.6G/62.7G swapfree 48.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.65 cpu 10.08 | cgroup 13.4G/max oom_kill 0 | free scratch 299.9G/44934409i tmp 26.1G/985940i workspace 299.9G/44934409i | repeat-01 collected 26/26 workers (60629 items) tests 20079 done 1 failed | 26 in flight, oldest 97s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.................................................................. [931%]
........................................................................ [934%]
..............................................................[contention-diag] +2717s soak 32p/221t rss 13.7G pss 12.3G swap 0.5G majflt 23236 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 4 descendant rss 0.0G pss 0.0G | host avail 24.0G/62.7G swapfree 48.1G/64.0G oom_kill +0 | psi10 mem 0.52/0.52 io 1.88 cpu 8.8 | cgroup 13.4G/max oom_kill 0 | free scratch 299.9G/44933479i tmp 26.1G/985940i workspace 299.9G/44933479i | repeat-01 collected 26/26 workers (60629 items) tests 20288 done 1 failed | 26 in flight, oldest 113s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.......... [937%]
........................................................................ [941%]
........................................................................ [944%]
.........................................[contention-diag] +2733s soak 31p/215t rss 13.6G pss 12.2G swap 0.5G majflt 23273 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.0G, 3 descendant rss 0.0G pss 0.0G | host avail 21.2G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.22/0.1 io 2.39 cpu 9.18 | cgroup 13.3G/max oom_kill 0 | free scratch 299.9G/44932742i tmp 26.1G/985940i workspace 299.9G/44932742i | repeat-01 collected 26/26 workers (60629 items) tests 20472 done 1 failed | 26 in flight, oldest 75s gw23 tests/ace/tui/widgets/test_prompt_tab_focus_steal.py::test_tab_after_background_refresh_stays_on_agents[refresh_display-insert]
............................... [947%]
........................................................................ [951%]
...............................................[contention-diag] +2748s soak 33p/215t rss 13.7G pss 12.3G swap 0.6G majflt 23310 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.0G, 5 descendant rss 0.1G pss 0.1G | host avail 19.1G/62.7G swapfree 47.8G/64.0G oom_kill +0 | psi10 mem 0.04/0.02 io 2.42 cpu 8.51 | cgroup 13.3G/max oom_kill 0 | free scratch 299.9G/44931802i tmp 26.1G/985940i workspace 299.9G/44931802i | scratch used 0.1G in 21665 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 20627 done 1 failed | 26 in flight, oldest 49s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_offline_reload_does_not_retain_freshness
......................... [954%]
........................................................................ [957%]
........................................................................ [961%]
.[contention-diag] +2766s soak 34p/205t rss 13.7G pss 12.3G swap 0.6G majflt 23394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.0G, 6 descendant rss 0.1G pss 0.0G | host avail 18.8G/62.7G swapfree 47.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.6 cpu 9.19 | cgroup 13.3G/max oom_kill 0 | free scratch 299.9G/44920707i tmp 26.1G/985940i workspace 299.9G/44920707i | repeat-01 collected 26/26 workers (60629 items) tests 20802 done 1 failed | 25 in flight, oldest 62s gw16 tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_already_absent_toasts
....................................................................... [964%]
........................................................................ [967%]
........................................................................ [971%]
...........................[contention-diag] +2781s soak 33p/212t rss 13.7G pss 12.3G swap 0.6G majflt 23460 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.0G, 5 descendant rss 0.1G pss 0.1G | host avail 18.9G/62.7G swapfree 47.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.43 cpu 10.32 | cgroup 13.3G/max oom_kill 0 | free scratch 299.8G/44912630i tmp 26.1G/985940i workspace 299.8G/44912630i | repeat-01 collected 26/26 workers (60629 items) tests 21044 done 1 failed | 26 in flight, oldest 56s gw9 tests/ace/tui/test_projects_pane.py::test_projects_filter_applies_once_per_keystroke
............................................. [974%]
........................................................................ [977%]
........................................................................ [981%]
..........................[contention-diag] +2796s soak 38p/216t rss 14.1G pss 12.5G swap 0.6G majflt 23490 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.0G, 10 descendant rss 0.4G pss 0.3G | host avail 18.1G/62.7G swapfree 46.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 16.59 cpu 8.86 | cgroup 13.6G/max oom_kill 0 | free scratch 299.8G/44909491i tmp 26.1G/985939i workspace 299.8G/44909491i | repeat-01 collected 26/26 workers (60629 items) tests 21259 done 1 failed | 25 in flight, oldest 50s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_failed_perf_load_keeps_the_active_view_rail
.............................................. [984%]
........................................................................ [987%]
........................................................................ [991%]
......................[contention-diag] +2812s soak 37p/213t rss 13.9G pss 12.4G swap 0.6G majflt 23590 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.0G, 9 descendant rss 0.3G pss 0.2G | host avail 16.9G/62.7G swapfree 47.0G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 18.97 cpu 8.04 | cgroup 13.5G/max oom_kill 0 | free scratch 299.9G/44911275i tmp 26.1G/985939i workspace 299.9G/44911275i | repeat-01 collected 26/26 workers (60629 items) tests 21476 done 1 failed | 26 in flight, oldest 52s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.................................................. [994%]
........................................................................ [997%]
.................................s.[contention-diag] +2827s soak 34p/213t rss 14.0G pss 12.5G swap 0.7G majflt 23728 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 11.9G, 6 descendant rss 0.4G pss 0.3G | host avail 17.4G/62.7G swapfree 46.9G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 14.34 cpu 8.98 | cgroup 13.5G/max oom_kill 0 | free scratch 299.8G/44903036i tmp 26.1G/985939i workspace 299.8G/44903036i | repeat-01 collected 26/26 workers (60629 items) tests 21632 done 1 failed | 26 in flight, oldest 67s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
..................................... [1001%]
........................................................................ [1004%]
....................................[contention-diag] +2843s soak 36p/211t rss 13.9G pss 12.4G swap 0.7G majflt 23801 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 11.9G, 8 descendant rss 0.4G pss 0.3G | host avail 17.2G/62.7G swapfree 46.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 5.13 cpu 9.71 | cgroup 13.5G/max oom_kill 0 | free scratch 299.8G/44900972i tmp 26.1G/985939i workspace 299.8G/44900972i | repeat-01 collected 26/26 workers (60629 items) tests 21777 done 1 failed | 26 in flight, oldest 83s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.................................... [1007%]
..................................................................[contention-diag] +2858s soak 36p/210t rss 14.0G pss 12.4G swap 0.7G majflt 23839 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 11.9G, 8 descendant rss 0.4G pss 0.3G | host avail 15.3G/62.7G swapfree 46.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.66 cpu 9.47 | cgroup 13.4G/max oom_kill 0 | free scratch 299.8G/44893103i tmp 26.1G/985939i workspace 299.8G/44893103i | repeat-01 collected 26/26 workers (60629 items) tests 21877 done 1 failed | 26 in flight, oldest 98s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
...... [1010%]
........................................................................ [1014%]
........................................................................ [1017%]
........................................................................ [1020%]
.........................[contention-diag] +2874s soak 36p/203t rss 13.9G pss 12.4G swap 0.7G majflt 24042 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 11.9G, 8 descendant rss 0.4G pss 0.3G | host avail 17.2G/62.7G swapfree 46.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.31 cpu 9.43 | cgroup 13.4G/max oom_kill 0 | free scratch 299.7G/44887947i tmp 26.1G/985939i workspace 299.7G/44887948i | scratch used 0.4G in 74088 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 22071 done 1 failed | 25 in flight, oldest 113s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
............................................... [1024%]
........................................................................ [1027%]
........................................................................ [1030%]
........................................................................ [1034%]
..............[contention-diag] +2891s soak 43p/219t rss 14.0G pss 12.5G swap 0.7G majflt 24276 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 11.9G, 15 descendant rss 0.5G pss 0.3G | host avail 20.9G/62.7G swapfree 46.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.67 cpu 9.96 | cgroup 13.5G/max oom_kill 0 | free scratch 299.7G/44879218i tmp 26.1G/985939i workspace 299.7G/44879218i | repeat-01 collected 26/26 workers (60629 items) tests 22393 done 1 failed | 26 in flight, oldest 131s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
.......................................................... [1037%]
........................................................................ [1040%]
........................................................................ [1044%]
.......................[contention-diag] +2906s soak 33p/201t rss 13.8G pss 12.2G swap 0.7G majflt 24406 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 11.9G, 5 descendant rss 0.2G pss 0.1G | host avail 18.1G/62.7G swapfree 46.5G/64.0G oom_kill +0 | psi10 mem 1.32/1.05 io 4.36 cpu 9.51 | cgroup 12.9G/max oom_kill 0 | free scratch 299.4G/44872524i tmp 26.1G/985938i workspace 299.4G/44872524i | repeat-01 collected 26/26 workers (60629 items) tests 22621 done 1 failed | 26 in flight, oldest 86s gw14 tests/test_docs_heading_anchors.py::test_page_heading_ids_match_python_markdown_toc
................................................. [1047%]
........................................................................ [1050%]
........................................................................ [1054%]
........................................................................ [1057%]
........................................................................ [1060%]
......................................................[contention-diag] +2924s soak 35p/189t rss 13.7G pss 12.1G swap 0.8G majflt 24795 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.2G pss 11.8G, 7 descendant rss 0.2G pss 0.1G | host avail 13.7G/62.7G swapfree 45.6G/64.0G oom_kill +0 | psi10 mem 16.72/13.93 io 14.43 cpu 8.96 | cgroup 12.3G/max oom_kill 0 | free scratch 299.4G/44868204i tmp 26.1G/985938i workspace 299.4G/44868204i | repeat-01 collected 26/26 workers (60629 items) tests 23016 done 1 failed | 25 in flight, oldest 57s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_description_rail_cannot_steal_focus_or_bindings
.................. [1064%]
................F[contention-failure] call tests/pager/test_app_dangling.py::test_unresolvable_label_toasts_marks_it_dangling_and_does_not_renavigate: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f4c9f44e900>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw17/test_unresolvable_label_toasts0')

    async def test_unresolvable_label_toasts_marks_it_dangling_and_does_not_renavigate(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        workspace = tmp_path / "ws"
        workspace.mkdir()
        loop_thread = threading.current_thread()
        git_calls: list[Path] = []
        resolve_threads: list[int | None] = []
    
        def fake_git(directory: Path) -> tuple[str, ...] | None:
            git_calls.append(directory)
            return ()
    
        def spy_resolve(
            ref: str, *, context: LinkResolutionContext | None = None
        ) -> LinkResolution:
            resolve_threads.append(threading.current_thread().ident)
            assert threading.current_thread() is not loop_thread
            return resolve_link(ref, context=context)
    
        monkeypatch.setattr("sase.pager._resolve_path_search._git_ls_files", fake_git)
        monkeypatch.setattr("sase.pager.screen.resolve_ref", spy_resolve)
        notifications: list[tuple[str, str]] = []
    
        def notify(message: str, *, severity: str = "information", **_kwargs: Any) -> None:
            notifications.append((message, severity))
    
        section = PagerSection(
            identity="file:/tmp/source.py",
            title="source.py",
            kind="file",
            body="see src/missing.py for details\n",
            link_anchors=(LinkAnchor(workspace),),
        )
        app = SasePager(
            PagerDocument(sections=(section,), title="source.py", origin=PagerOrigin.FILE)
        )
        monkeypatch.setattr(app, "notify", notify)
        async with app.run_test(size=(80, 24)) as pilot:
            screen = pager_screen(app)
            await pilot.pause()
            await pilot.press("0")
            await pilot.pause(0.1)
            await pilot.pause(0.1)
    
>           assert git_calls == [workspace.resolve()]
E           AssertionError: assert [] == [PosixPath('/..._toasts0/ws')]
E             
E             Right contains one more item: PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw17/test_unresolvable_label_toasts0/ws')
E             Use -v to get more diff

tests/pager/test_app_dangling.py:65: AssertionError
....................................................... [1067%]
........................................................................ [1070%]
........................................................................ [1074%]
........................................................................ [1077%]
...[contention-diag] +2939s soak 37p/199t rss 11.6G pss 10.0G swap 3.1G majflt 28666 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.1G pss 9.6G, 9 descendant rss 0.3G pss 0.2G | host avail 18.4G/62.7G swapfree 42.7G/64.0G oom_kill +0 | psi10 mem 27.44/22.52 io 24.26 cpu 6.93 | cgroup 10.3G/max oom_kill 0 | free scratch 299.3G/44864685i tmp 26.1G/985938i workspace 299.3G/44864685i | repeat-01 collected 26/26 workers (60629 items) tests 23316 done 2 failed | 26 in flight, oldest 57s gw2 tests/main/test_artifact_link_outbox_io.py::test_caller_supplied_id_append_scans_only_matching_lines
..................................................................... [1080%]
........................................................................ [1084%]
........................................................................ [1087%]
........................................................................ [1090%]
........................................................[contention-diag] +2954s soak 36p/189t rss 11.6G pss 10.0G swap 3.0G majflt 38924 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 9.7G, 8 descendant rss 0.3G pss 0.2G | host avail 19.2G/62.7G swapfree 42.8G/64.0G oom_kill +0 | psi10 mem 6.22/4.55 io 8.98 cpu 8.56 | cgroup 10.4G/max oom_kill 0 | free scratch 299.3G/44859008i tmp 26.1G/985938i workspace 299.3G/44859008i | repeat-01 collected 26/26 workers (60629 items) tests 23665 done 2 failed | 26 in flight, oldest 72s gw2 tests/main/test_artifact_link_outbox_io.py::test_caller_supplied_id_append_scans_only_matching_lines
................ [1094%]
........................................................................ [1097%]
........................................................................ [1100%]
........................................................................ [1104%]
...............................................[contention-diag] +2970s soak 37p/202t rss 11.7G pss 10.1G swap 3.0G majflt 44815 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.2G pss 9.7G, 9 descendant rss 0.3G pss 0.2G | host avail 17.5G/62.7G swapfree 42.8G/64.0G oom_kill +0 | psi10 mem 1.71/1.12 io 8.97 cpu 10.08 | cgroup 10.5G/max oom_kill 0 | free scratch 299.1G/44853898i tmp 26.1G/985938i workspace 299.1G/44853898i | repeat-01 collected 26/26 workers (60629 items) tests 23940 done 2 failed | 25 in flight, oldest 88s gw2 tests/main/test_artifact_link_outbox_io.py::test_caller_supplied_id_append_scans_only_matching_lines
......................... [1107%]
........................................................................ [1110%]
........................................................................ [1114%]
.................................................[contention-diag] +2985s soak 34p/203t rss 11.7G pss 10.1G swap 2.9G majflt 66526 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 9.9G, 6 descendant rss 0.2G pss 0.1G | host avail 17.1G/62.7G swapfree 42.8G/64.0G oom_kill +0 | psi10 mem 1.14/0.22 io 7.88 cpu 8.53 | cgroup 10.6G/max oom_kill 0 | free scratch 299.0G/44851640i tmp 26.1G/985938i workspace 299.0G/44851640i | repeat-01 collected 26/26 workers (60629 items) tests 24168 done 2 failed | 26 in flight, oldest 103s gw2 tests/main/test_artifact_link_outbox_io.py::test_caller_supplied_id_append_scans_only_matching_lines
....................... [1117%]
........................................................................ [1120%]
........................................................................ [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
.........[contention-diag] +3001s soak 36p/214t rss 11.8G pss 10.2G swap 2.8G majflt 84945 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.5G pss 10.0G, 8 descendant rss 0.2G pss 0.0G | host avail 16.0G/62.7G swapfree 42.8G/64.0G oom_kill +0 | psi10 mem 1.04/0.04 io 5.67 cpu 9.9 | cgroup 10.7G/max oom_kill 0 | free scratch 299.0G/44846645i tmp 26.1G/985938i workspace 299.0G/44846645i | scratch used 0.1G in 11338 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 24434 done 2 failed | 26 in flight, oldest 78s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
......................s........................................ [1134%]
........................................................................ [1137%]
........................................................................ [1140%]
.....................................................[contention-diag] +3018s soak 33p/188t rss 11.9G pss 10.3G swap 2.6G majflt 105864 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.1G, 5 descendant rss 0.1G pss 0.1G | host avail 14.9G/62.7G swapfree 42.9G/64.0G oom_kill +0 | psi10 mem 0.92/0.0 io 3.04 cpu 9.39 | cgroup 11.2G/max oom_kill 0 | free scratch 298.7G/44841793i tmp 26.1G/985938i workspace 298.7G/44841793i | repeat-01 collected 26/26 workers (60629 items) tests 24729 done 2 failed | 25 in flight, oldest 91s gw11 tests/ace/tui/test_tribe_panel_flicker_display.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
................... [1144%]
........................................................................ [1147%]
........................................................................ [1150%]
........................................................................ [1153%]
[contention-diag] +3033s soak 29p/165t rss 11.8G pss 10.3G swap 2.6G majflt 119032 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 19.7G/62.7G swapfree 42.9G/64.0G oom_kill +0 | psi10 mem 0.88/0.0 io 4.32 cpu 8.52 | cgroup 10.8G/max oom_kill 0 | free scratch 298.6G/44837118i tmp 26.1G/985937i workspace 298.6G/44837118i | repeat-01 collected 26/26 workers (60629 items) tests 24978 done 2 failed | 26 in flight, oldest 87s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
........................................................................ [1157%]
........................................................................ [1160%]
..............................[contention-diag] +3049s soak 30p/174t rss 11.6G pss 10.1G swap 2.8G majflt 143626 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 9.9G, 2 descendant rss 0.0G pss 0.0G | host avail 18.4G/62.7G swapfree 42.5G/64.0G oom_kill +0 | psi10 mem 2.33/0.56 io 3.37 cpu 8.19 | cgroup 10.6G/max oom_kill 0 | free scratch 298.4G/44833616i tmp 26.1G/985937i workspace 298.4G/44833616i | repeat-01 collected 26/26 workers (60629 items) tests 25158 done 2 failed | 26 in flight, oldest 102s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
.......................................... [1163%]
........................................................................ [1167%]
..............................................[contention-diag] +3064s soak 39p/195t rss 12.2G pss 10.5G swap 2.7G majflt 162962 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.1G, 11 descendant rss 0.4G pss 0.3G | host avail 17.6G/62.7G swapfree 42.5G/64.0G oom_kill +0 | psi10 mem 3.09/0.13 io 2.55 cpu 8.99 | cgroup 11.1G/max oom_kill 0 | free scratch 298.1G/44825781i tmp 26.1G/985937i workspace 298.1G/44825781i | repeat-01 collected 26/26 workers (60629 items) tests 25317 done 2 failed | 25 in flight, oldest 118s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
.......................... [1170%]
........................................................................ [1173%]
............[contention-diag] +3080s soak 31p/172t rss 11.9G pss 10.3G swap 2.6G majflt 168712 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.1G, 3 descendant rss 0.1G pss 0.0G | host avail 17.3G/62.7G swapfree 42.5G/64.0G oom_kill +0 | psi10 mem 1.42/0.02 io 42.4 cpu 5.44 | cgroup 10.9G/max oom_kill 0 | free scratch 298.0G/44814500i tmp 26.1G/985937i workspace 298.0G/44814500i | repeat-01 collected 26/26 workers (60629 items) tests 25427 done 2 failed | 26 in flight, oldest 133s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
............................................................ [1177%]
........................................................................ [1180%]
........................................................................ [1183%]
....................[contention-diag] +3095s soak 31p/166t rss 10.9G pss 9.4G swap 3.6G majflt 175311 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 9.2G, 3 descendant rss 0.0G pss 0.0G | host avail 14.9G/62.7G swapfree 40.5G/64.0G oom_kill +0 | psi10 mem 8.55/5.84 io 16.24 cpu 17.0 | cgroup 9.9G/max oom_kill 0 | free scratch 297.6G/44798768i tmp 26.1G/985581i workspace 297.6G/44798768i | repeat-01 collected 26/26 workers (60629 items) tests 25646 done 2 failed | 25 in flight, oldest 149s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
.................................................... [1187%]
........................................................................ [1190%]
........................................................................ [1193%]
........................................................................ [1197%]
...................[contention-diag] +3111s soak 33p/172t rss 10.8G pss 9.3G swap 3.7G majflt 205785 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.1G, 5 descendant rss 0.0G pss 0.0G | host avail 18.6G/62.7G swapfree 39.7G/64.0G oom_kill +0 | psi10 mem 4.34/2.82 io 6.01 cpu 13.06 | cgroup 9.8G/max oom_kill 0 | free scratch 297.6G/44795149i tmp 26.1G/985862i workspace 297.6G/44795149i | repeat-01 collected 26/26 workers (60629 items) tests 25924 done 2 failed | 25 in flight, oldest 165s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
..................................................... [1200%]
.................................................F[contention-failure] call tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/test_three_update_cycles_refre0')
capsys = <_pytest.capture.CaptureFixture object at 0x7f8d13fabd10>

    def test_three_update_cycles_refresh_bash_fish_and_zsh(
        tmp_path: Path,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        scripts = install_unmanaged_shells(tmp_path)
        mark_scripts_stale(scripts)
        for stamp in (read_stamp(shell) for shell in scripts):
            assert stamp is not None
            assert stamp.version == OLD_STAMP_VERSION
    
        snapshots: list[dict[str, str]] = []
        for _ in range(SOAK_CYCLES):
            payload = successful_update(tmp_path, capsys)
>           assert_unmanaged_refresh(scripts, payload)

tests/completion/test_update_refresh_soak.py:63: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

scripts = {'bash': PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/test_three_update_cycles_refre0/complet...th('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/test_three_update_cycles_refre0/completions/zsh/_sase')}
payload = {'changed': True, 'command': ['uv', 'tool', 'upgrade', '--color', 'never', 'sase'], 'completion_refresh': {'attempted'...hree_update_cycles_refre0/completions/zsh/_sase'}]}, 'counts': {'already_current': 1, 'removed': 0, 'updated': 2}, ...}

    def assert_unmanaged_refresh(
        scripts: Mapping[str, Path],
        payload: Mapping[str, Any],
        *,
        exact: bool = True,
    ) -> None:
        """Assert a successful refresh rewrote stamps, scripts, and zsh bytecode."""
        wanted = tuple(scripts)
        by_shell = refresh_by_shell(payload)
        if exact:
            assert set(by_shell) == set(wanted)
        else:
            assert set(wanted) <= set(by_shell)
        for shell in wanted:
            outcome = by_shell[shell]
            script = scripts[shell]
            text = script.read_text(encoding="utf-8")
>           assert outcome["ok"] is True, outcome
                   ^^^^^^^^^^^^^^^^^^^^^
E           AssertionError: {'detail': 'zcompile timed out for /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/home-5fvdevc8/.sase/completion/grammar/1cd4bfe2cc6377809108cf83/zsh/.stage.1733152/._sase.1733152.tmp', 'ok': False, 'shell': 'zsh', 'target': '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/test_three_update_cycles_refre0/completions/zsh/_sase'}

tests/completion/_update_refresh_harness.py:125: AssertionError
...................... [1203%]
.................................[contention-diag] +3127s soak 31p/174t rss 11.2G pss 9.7G swap 3.4G majflt 258854 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.5G, 3 descendant rss 0.1G pss 0.1G | host avail 14.3G/62.7G swapfree 39.8G/64.0G oom_kill +0 | psi10 mem 0.87/0.56 io 2.32 cpu 27.18 | cgroup 10.2G/max oom_kill 0 | free scratch 297.2G/44792649i tmp 26.1G/985883i workspace 297.2G/44792649i | scratch used 0.1G in 11957 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 26085 done 3 failed | 26 in flight, oldest 181s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....................................... [1207%]
........................................................................ [1210%]
...................................[contention-diag] +3144s soak 31p/170t rss 11.6G pss 10.0G swap 3.1G majflt 295101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 9.8G, 3 descendant rss 0.1G pss 0.1G | host avail 17.3G/62.7G swapfree 39.8G/64.0G oom_kill +0 | psi10 mem 0.17/0.11 io 3.42 cpu 14.48 | cgroup 10.5G/max oom_kill 0 | free scratch 297.1G/44788770i tmp 26.1G/985883i workspace 297.1G/44788770i | repeat-01 collected 26/26 workers (60629 items) tests 26227 done 3 failed | 25 in flight, oldest 198s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
..................................... [1213%]
........................................................................ [1217%]
........................................................................ [1220%]
........................................................................ [1223%]
........................[contention-diag] +3160s soak 29p/170t rss 11.5G pss 10.0G swap 3.0G majflt 304453 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 23.0G/62.7G swapfree 39.8G/64.0G oom_kill +0 | psi10 mem 0.56/0.02 io 6.14 cpu 11.6 | cgroup 10.5G/max oom_kill 0 | free scratch 297.1G/44785375i tmp 26.1G/985910i workspace 297.1G/44785375i | repeat-01 collected 26/26 workers (60629 items) tests 26510 done 3 failed | 25 in flight, oldest 214s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................ [1227%]
........................................................................ [1230%]
........................................................................ [1233%]
........................................................................ [1237%]
....................................[contention-diag] +3175s soak 33p/175t rss 11.8G pss 10.1G swap 2.9G majflt 327309 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.5G pss 10.0G, 5 descendant rss 0.1G pss 0.0G | host avail 22.0G/62.7G swapfree 39.9G/64.0G oom_kill +0 | psi10 mem 0.53/0.0 io 9.47 cpu 9.9 | cgroup 10.7G/max oom_kill 0 | free scratch 297.1G/44782429i tmp 26.1G/985912i workspace 297.1G/44782429i | repeat-01 collected 26/26 workers (60629 items) tests 26817 done 3 failed | 26 in flight, oldest 229s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................................... [1240%]
........................................................................ [1243%]
.......................................................[contention-diag] +3191s soak 32p/169t rss 11.9G pss 10.2G swap 2.8G majflt 340631 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.0G, 4 descendant rss 0.1G pss 0.1G | host avail 20.1G/62.7G swapfree 39.9G/64.0G oom_kill +0 | psi10 mem 0.38/0.0 io 9.51 cpu 8.54 | cgroup 10.9G/max oom_kill 0 | free scratch 297.1G/44780161i tmp 26.1G/985912i workspace 297.1G/44780161i | repeat-01 collected 26/26 workers (60629 items) tests 26964 done 3 failed | 26 in flight, oldest 245s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................. [1247%]
........................................................................ [1250%]
.............................[contention-diag] +3206s soak 35p/176t rss 12.2G pss 10.5G swap 2.7G majflt 354416 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.7G pss 10.2G, 7 descendant rss 0.3G pss 0.2G | host avail 22.0G/62.7G swapfree 39.9G/64.0G oom_kill +0 | psi10 mem 0.22/0.0 io 6.1 cpu 9.2 | cgroup 11.1G/max oom_kill 0 | free scratch 297.1G/44777857i tmp 26.1G/985912i workspace 297.1G/44777857i | repeat-01 collected 26/26 workers (60629 items) tests 27089 done 3 failed | 26 in flight, oldest 260s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................................... [1253%]
........................................................................ [1257%]
.[contention-diag] +3222s soak 36p/166t rss 12.2G pss 10.6G swap 2.6G majflt 375113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.8G pss 10.3G, 8 descendant rss 0.3G pss 0.2G | host avail 20.8G/62.7G swapfree 39.9G/64.0G oom_kill +0 | psi10 mem 0.84/0.79 io 5.26 cpu 9.65 | cgroup 11.1G/max oom_kill 0 | free scratch 297.0G/44775920i tmp 26.1G/985912i workspace 297.0G/44775920i | repeat-01 collected 26/26 workers (60629 items) tests 27216 done 3 failed | 25 in flight, oldest 275s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
....................................................................... [1260%]
.............................................[contention-diag] +3237s soak 33p/164t rss 12.3G pss 10.6G swap 2.5G majflt 401131 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.9G pss 10.4G, 5 descendant rss 0.2G pss 0.2G | host avail 19.4G/62.7G swapfree 39.9G/64.0G oom_kill +0 | psi10 mem 0.16/0.15 io 4.42 cpu 9.71 | cgroup 11.0G/max oom_kill 0 | free scratch 297.5G/44771618i tmp 26.1G/985911i workspace 297.5G/44771618i | repeat-01 collected 26/26 workers (60629 items) tests 27321 done 3 failed | 25 in flight, oldest 291s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................... [1263%]
........................................................................ [1267%]
........................................................................ [1270%]
........................................................................ [1273%]
........................................................................ [1277%]
........................................................................ [1280%]
........................................................................ [1283%]
..........[contention-diag] +3253s soak 34p/185t rss 12.3G pss 10.7G swap 2.5G majflt 431301 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 12.0G pss 10.4G, 6 descendant rss 0.3G pss 0.2G | host avail 20.5G/62.7G swapfree 39.4G/64.0G oom_kill +0 | psi10 mem 0.69/0.12 io 4.54 cpu 9.35 | cgroup 11.1G/max oom_kill 0 | free scratch 297.5G/44768083i tmp 26.1G/985911i workspace 297.5G/44768083i | scratch used 0.1G in 12456 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 27729 done 3 failed | 24 in flight, oldest 306s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.............................................................. [1287%]
........................................................................ [1290%]
.......................................................................[contention-diag] +3270s soak 35p/168t rss 12.5G pss 10.9G swap 2.3G majflt 468797 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.2G pss 10.6G, 7 descendant rss 0.2G pss 0.2G | host avail 18.3G/62.7G swapfree 39.3G/64.0G oom_kill +0 | psi10 mem 1.21/0.28 io 3.31 cpu 8.61 | cgroup 11.3G/max oom_kill 0 | free scratch 297.4G/44762385i tmp 26.1G/985911i workspace 297.4G/44762385i | repeat-01 collected 26/26 workers (60629 items) tests 28007 done 3 failed | 25 in flight, oldest 324s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
. [1293%]
........................................................................ [1296%]
........................................................................ [1300%]
........................................................................ [1303%]
........................................................................ [1306%]
...........................[contention-diag] +3285s soak 31p/169t rss 12.4G pss 10.8G swap 2.2G majflt 489114 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 12.3G pss 10.7G, 3 descendant rss 0.0G pss 0.0G | host avail 17.3G/62.7G swapfree 39.5G/64.0G oom_kill +0 | psi10 mem 0.72/0.12 io 2.43 cpu 8.02 | cgroup 11.2G/max oom_kill 0 | free scratch 297.3G/44755957i tmp 26.1G/985911i workspace 297.3G/44755957i | repeat-01 collected 26/26 workers (60629 items) tests 28292 done 3 failed | 25 in flight, oldest 339s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
............................................. [1310%]
........................................................................ [1313%]
........................................................................ [1316%]
........................................................................ [1320%]
........................................................................ [1323%]
........................................................................ [1326%]
.....................................[contention-diag] +3301s soak 31p/162t rss 12.6G pss 11.0G swap 2.1G majflt 515210 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.4G pss 10.9G, 3 descendant rss 0.1G pss 0.1G | host avail 15.9G/62.7G swapfree 39.5G/64.0G oom_kill +0 | psi10 mem 1.11/0.02 io 3.64 cpu 9.14 | cgroup 11.6G/max oom_kill 0 | free scratch 297.4G/44752389i tmp 26.1G/985911i workspace 297.4G/44752389i | repeat-01 collected 26/26 workers (60629 items) tests 28747 done 3 failed | 23 in flight, oldest 354s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................... [1330%]
........................................................................ [1333%]
........................................................................ [1336%]
........................................................................ [1340%]
........................................................................ [1343%]
........................................................................ [1346%]
................................................[contention-diag] +3316s soak 36p/171t rss 12.5G pss 10.9G swap 2.2G majflt 531738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.3G pss 10.7G, 8 descendant rss 0.2G pss 0.1G | host avail 16.5G/62.7G swapfree 39.0G/64.0G oom_kill +0 | psi10 mem 1.43/0.15 io 3.73 cpu 8.24 | cgroup 11.4G/max oom_kill 0 | free scratch 297.0G/44748745i tmp 26.1G/985911i workspace 297.0G/44748745i | repeat-01 collected 26/26 workers (60629 items) tests 29199 done 3 failed | 25 in flight, oldest 292s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
........................ [1350%]
........................................................................ [1353%]
........................................................................ [1356%]
..........................................[contention-diag] +3332s soak 36p/173t rss 12.3G pss 10.7G swap 2.4G majflt 536947 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.2G pss 10.6G, 8 descendant rss 0.1G pss 0.0G | host avail 19.3G/62.7G swapfree 39.2G/64.0G oom_kill +0 | psi10 mem 1.31/0.5 io 4.46 cpu 8.47 | cgroup 11.2G/max oom_kill 0 | free scratch 296.9G/44744063i tmp 26.1G/985911i workspace 296.9G/44744063i | repeat-01 collected 26/26 workers (60629 items) tests 29414 done 3 failed | 25 in flight, oldest 307s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.............................. [1360%]
........................................................................ [1363%]
........................................................................ [1366%]
........................................................................ [1370%]
...[contention-diag] +3347s soak 32p/167t rss 12.4G pss 10.8G swap 2.3G majflt 543639 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.2G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 19.3G/62.7G swapfree 39.3G/64.0G oom_kill +0 | psi10 mem 0.32/0.12 io 2.89 cpu 9.1 | cgroup 11.4G/max oom_kill 0 | free scratch 296.9G/44738154i tmp 26.1G/985911i workspace 296.9G/44738154i | repeat-01 collected 26/26 workers (60629 items) tests 29655 done 3 failed | 25 in flight, oldest 323s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
..................................................................... [1373%]
........................................................................ [1376%]
...............................................[contention-diag] +3362s soak 33p/169t rss 12.6G pss 11.0G swap 2.2G majflt 565783 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.4G pss 10.8G, 5 descendant rss 0.1G pss 0.1G | host avail 19.2G/62.7G swapfree 39.3G/64.0G oom_kill +0 | psi10 mem 0.06/0.02 io 7.32 cpu 8.18 | cgroup 11.5G/max oom_kill 0 | free scratch 297.2G/44734448i tmp 26.1G/985910i workspace 297.2G/44734449i | repeat-01 collected 26/26 workers (60629 items) tests 29854 done 3 failed | 25 in flight, oldest 338s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
......................... [1380%]
........................................................................ [1383%]
........................................................................ [1386%]
..............[contention-diag] +3378s soak 33p/166t rss 12.8G pss 11.2G swap 1.9G majflt 594553 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.6G pss 11.0G, 5 descendant rss 0.1G pss 0.1G | host avail 17.9G/62.7G swapfree 39.3G/64.0G oom_kill +0 | psi10 mem 0.39/0.28 io 5.07 cpu 8.79 | cgroup 11.7G/max oom_kill 0 | free scratch 296.7G/44731631i tmp 26.1G/985910i workspace 296.7G/44731631i | scratch used 0.2G in 27704 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 30019 done 3 failed | 25 in flight, oldest 354s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.......................................................... [1390%]
........................................................................ [1393%]
........................................................................ [1396%]
........................................................................ [1400%]
........................................................................ [1403%]
.....................[contention-diag] +3395s soak 35p/165t rss 13.0G pss 11.3G swap 1.9G majflt 603830 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.7G pss 11.1G, 7 descendant rss 0.2G pss 0.2G | host avail 18.6G/62.7G swapfree 39.4G/64.0G oom_kill +0 | psi10 mem 0.07/0.05 io 3.34 cpu 10.14 | cgroup 11.9G/max oom_kill 0 | free scratch 296.6G/44725818i tmp 26.1G/985910i workspace 296.6G/44725818i | repeat-01 collected 26/26 workers (60629 items) tests 30368 done 3 failed | 25 in flight, oldest 371s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
................................................... [1406%]
........................................................................ [1410%]
........................................................................ [1413%]
........................................................................ [1416%]
........................................................................ [1420%]
........................................................................ [1423%]
...............................[contention-diag] +3411s soak 38p/171t rss 13.1G pss 11.3G swap 1.9G majflt 604698 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.7G pss 11.1G, 10 descendant rss 0.3G pss 0.2G | host avail 18.9G/62.7G swapfree 39.4G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.39 cpu 10.68 | cgroup 11.9G/max oom_kill 0 | free scratch 296.7G/44721190i tmp 26.1G/985909i workspace 296.7G/44721190i | repeat-01 collected 26/26 workers (60629 items) tests 30830 done 3 failed | 25 in flight, oldest 386s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
......................................... [1426%]
........................................................................ [1430%]
........................................................................ [1433%]
..............................................................[contention-diag] +3426s soak 39p/167t rss 13.1G pss 11.4G swap 1.9G majflt 606013 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.7G pss 11.1G, 11 descendant rss 0.2G pss 0.2G | host avail 18.1G/62.7G swapfree 39.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.0 cpu 9.82 | cgroup 12.1G/max oom_kill 0 | free scratch 296.6G/44717037i tmp 26.1G/985908i workspace 296.6G/44717037i | repeat-01 collected 26/26 workers (60629 items) tests 31080 done 3 failed | 25 in flight, oldest 402s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.......... [1436%]
........................................................................ [1440%]
........................................................................ [1443%]
....................................................................[contention-diag] +3441s soak 35p/176t rss 13.1G pss 11.4G swap 1.8G majflt 616001 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.8G pss 11.2G, 7 descendant rss 0.2G pss 0.1G | host avail 18.4G/62.7G swapfree 39.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.74 cpu 9.52 | cgroup 11.9G/max oom_kill 0 | free scratch 296.6G/44714239i tmp 26.1G/985908i workspace 296.6G/44714239i | repeat-01 collected 26/26 workers (60629 items) tests 31296 done 3 failed | 25 in flight, oldest 417s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.... [1446%]
........................................................................ [1449%]
........................................................................ [1453%]
........................................................................ [1456%]
.....................................................................[contention-diag] +3457s soak 34p/174t rss 13.1G pss 11.5G swap 1.7G majflt 629081 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 12.9G pss 11.3G, 6 descendant rss 0.2G pss 0.1G | host avail 17.1G/62.7G swapfree 39.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.41 cpu 10.17 | cgroup 12.0G/max oom_kill 0 | free scratch 296.6G/44712079i tmp 26.1G/985908i workspace 296.6G/44712079i | repeat-01 collected 26/26 workers (60629 items) tests 31595 done 3 failed | 24 in flight, oldest 433s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
... [1459%]
........................................................................ [1463%]
........................................................................ [1466%]
....[contention-diag] +3472s soak 33p/167t rss 13.3G pss 11.6G swap 1.6G majflt 640680 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.4G, 5 descendant rss 0.2G pss 0.1G | host avail 17.3G/62.7G swapfree 39.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.68 cpu 9.7 | cgroup 12.2G/max oom_kill 0 | free scratch 296.6G/44707137i tmp 26.1G/985908i workspace 296.6G/44707137i | repeat-01 collected 26/26 workers (60629 items) tests 31756 done 3 failed | 24 in flight, oldest 448s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.................................................................... [1469%]
....................................................................[contention-diag] +3488s soak 35p/176t rss 13.4G pss 11.7G swap 1.6G majflt 641926 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.4G, 7 descendant rss 0.3G pss 0.2G | host avail 20.8G/62.7G swapfree 39.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.72 cpu 9.84 | cgroup 12.3G/max oom_kill 0 | free scratch 296.6G/44703976i tmp 26.1G/985908i workspace 296.6G/44703976i | repeat-01 collected 26/26 workers (60629 items) tests 31888 done 3 failed | 24 in flight, oldest 463s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
.... [1473%]
........................................................................ [1476%]
........................................................................ [1479%]
........................................................................ [1483%]
............[contention-diag] +3503s soak 40p/195t rss 13.4G pss 11.6G swap 1.6G majflt 642407 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.4G, 12 descendant rss 0.2G pss 0.2G | host avail 20.5G/62.7G swapfree 39.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.07 cpu 9.44 | cgroup 12.2G/max oom_kill 0 | free scratch 296.6G/44702164i tmp 26.1G/985908i workspace 296.6G/44702164i | scratch used 0.2G in 40915 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 32097 done 3 failed | 24 in flight, oldest 479s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
............................................................ [1486%]
........................................................................ [1489%]
........................................................................ [1493%]
...................[contention-diag] +3521s soak 37p/179t rss 13.4G pss 11.6G swap 1.6G majflt 642929 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.4G, 9 descendant rss 0.2G pss 0.1G | host avail 20.7G/62.7G swapfree 39.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.04 cpu 9.81 | cgroup 12.3G/max oom_kill 0 | free scratch 296.5G/44698664i tmp 26.1G/985908i workspace 296.5G/44698664i | repeat-01 collected 26/26 workers (60629 items) tests 32334 done 3 failed | 24 in flight, oldest 212s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
..................................................... [1496%]
........................................................................ [1499%]
........................................................................ [1503%]
........................................................................ [1506%]
........................................................................ [1509%]
.[contention-diag] +3536s soak 35p/162t rss 13.4G pss 11.7G swap 1.6G majflt 643462 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.0G pss 11.4G, 7 descendant rss 0.2G pss 0.2G | host avail 20.5G/62.7G swapfree 39.7G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 2.11 cpu 9.96 | cgroup 12.3G/max oom_kill 0 | free scratch 296.5G/44695539i tmp 26.1G/985908i workspace 296.5G/44695539i | repeat-01 collected 26/26 workers (60629 items) tests 32664 done 3 failed | 23 in flight, oldest 227s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
....................................................................... [1513%]
........................................................................ [1516%]
........................................................................ [1519%]
........................................................................ [1523%]
.........................................[contention-diag] +3552s soak 34p/167t rss 13.4G pss 11.7G swap 1.6G majflt 645604 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 13.1G pss 11.5G, 6 descendant rss 0.2G pss 0.1G | host avail 19.9G/62.7G swapfree 39.7G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.62 cpu 10.41 | cgroup 12.4G/max oom_kill 0 | free scratch 296.5G/44691253i tmp 26.1G/985908i workspace 296.5G/44691253i | repeat-01 collected 26/26 workers (60629 items) tests 33000 done 3 failed | 24 in flight, oldest 243s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
[contention-diag] +3567s soak 34p/171t rss 13.5G pss 11.8G swap 1.4G majflt 664401 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.5G, 6 descendant rss 0.1G pss 0.1G | host avail 19.6G/62.7G swapfree 40.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.37 cpu 9.02 | cgroup 12.5G/max oom_kill 0 | free scratch 296.5G/44689135i tmp 26.1G/985908i workspace 296.5G/44689135i | repeat-01 collected 26/26 workers (60629 items) tests 33000 done 3 failed | 24 in flight, oldest 258s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................... [1526%]
........................................................................ [1529%]
........................................................................ [1533%]
........................................................................ [1536%]
........................................................................ [1539%]
........................................................................ [1543%]
........................................................................ [1546%]
....................................[contention-diag] +3582s soak 36p/177t rss 13.6G pss 11.9G swap 1.4G majflt 665263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.4G, 8 descendant rss 0.3G pss 0.2G | host avail 18.5G/62.7G swapfree 40.1G/64.0G oom_kill +0 | psi10 mem 0.36/0.0 io 0.95 cpu 9.65 | cgroup 12.6G/max oom_kill 0 | free scratch 296.5G/44685662i tmp 26.1G/985908i workspace 296.5G/44685662i | repeat-01 collected 26/26 workers (60629 items) tests 33498 done 3 failed | 24 in flight, oldest 274s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
.................................... [1549%]
........................................................................ [1553%]
........................................................................ [1556%]
........................................................................ [1559%]
........................................................................ [1563%]
........................................................................ [1566%]
........................................................................ [1569%]
........................................................................ [1573%]
........................................................................ [1576%]
...............[contention-diag] +3598s soak 32p/171t rss 13.6G pss 11.9G swap 1.4G majflt 666083 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.5G, 4 descendant rss 0.2G pss 0.2G | host avail 19.2G/62.7G swapfree 40.1G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 1.45 cpu 9.5 | cgroup 12.6G/max oom_kill 0 | free scratch 296.5G/44682191i tmp 26.1G/985908i workspace 296.5G/44682191i | repeat-01 collected 26/26 workers (60629 items) tests 34105 done 3 failed | 24 in flight, oldest 289s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
......................................................... [1579%]
........................................................................ [1583%]
........................................................................ [1586%]
........................................................................ [1589%]
............................................[contention-diag] +3613s soak 33p/172t rss 13.6G pss 11.9G swap 1.4G majflt 666638 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.4G, 5 descendant rss 0.2G pss 0.2G | host avail 19.4G/62.7G swapfree 40.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 1.34 cpu 9.28 | cgroup 12.6G/max oom_kill 0 | free scratch 296.3G/44679034i tmp 26.1G/985908i workspace 296.3G/44679034i | repeat-01 collected 26/26 workers (60629 items) tests 34444 done 3 failed | 24 in flight, oldest 304s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
............................ [1592%]
........................................................................ [1596%]
........................................................................ [1599%]
........................................................................ [1602%]
........................................................................ [1606%]
.............[contention-diag] +3628s soak 33p/160t rss 13.6G pss 11.8G swap 1.5G majflt 667084 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.3G, 5 descendant rss 0.3G pss 0.2G | host avail 18.9G/62.7G swapfree 39.7G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 1.17 cpu 8.81 | cgroup 12.7G/max oom_kill 0 | free scratch 296.3G/44676798i tmp 26.1G/985908i workspace 296.3G/44676798i | scratch used 0.3G in 54126 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 34726 done 3 failed | 24 in flight, oldest 320s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 1 hazardous kill call(s)
........................................................... [1609%]
........................................................................ [1612%]
........................................................................ [1616%]
............................................................s........... [1619%]
........................................................................ [1622%]
.........................................................[contention-diag] +3646s soak 35p/178t rss 13.6G pss 11.8G swap 1.5G majflt 667919 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.4G, 7 descendant rss 0.3G pss 0.2G | host avail 19.8G/62.7G swapfree 39.7G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.03 cpu 9.43 | cgroup 12.9G/max oom_kill 0 | free scratch 296.3G/44673223i tmp 26.1G/985908i workspace 296.3G/44673223i | repeat-01 collected 26/26 workers (60629 items) tests 35191 done 3 failed | 24 in flight, oldest 337s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 2 hazardous kill call(s)
............... [1626%]
........................................................................ [1629%]
........................................................................ [1632%]
........................................................................ [1636%]
........................................................................ [1639%]
.....................[contention-diag] +3661s soak 31p/182t rss 13.5G pss 11.8G swap 1.5G majflt 668731 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.0G pss 11.4G, 3 descendant rss 0.1G pss 0.1G | host avail 18.5G/62.7G swapfree 39.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.01 cpu 9.55 | cgroup 12.8G/max oom_kill 0 | free scratch 296.3G/44685890i tmp 26.1G/985908i workspace 296.3G/44685890i | repeat-01 collected 26/26 workers (60629 items) tests 35509 done 3 failed | 24 in flight, oldest 353s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
................................................... [1642%]
........................................................................ [1646%]
........................................................................ [1649%]
............................................[contention-diag] +3677s soak 32p/182t rss 13.5G pss 11.7G swap 1.5G majflt 669027 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.4G, 4 descendant rss 0.1G pss 0.0G | host avail 35.8G/62.7G swapfree 41.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.38 cpu 12.24 | cgroup 12.7G/max oom_kill 0 | free scratch 296.3G/44689694i tmp 26.1G/985909i workspace 296.3G/44689694i | repeat-01 collected 26/26 workers (60629 items) tests 35755 done 3 failed | 24 in flight, oldest 368s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
............................ [1652%]
........................................................................ [1656%]
........................................................................ [1659%]
....................................................[contention-diag] +3692s soak 33p/184t rss 13.6G pss 11.9G swap 1.5G majflt 672389 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.5G, 5 descendant rss 0.2G pss 0.2G | host avail 36.3G/62.7G swapfree 41.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.7 cpu 19.41 | cgroup 12.8G/max oom_kill 0 | free scratch 296.3G/44689144i tmp 26.1G/985909i workspace 296.3G/44689144i | repeat-01 collected 26/26 workers (60629 items) tests 35969 done 3 failed | 24 in flight, oldest 383s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
.................... [1662%]
........................................................................ [1666%]
........................................................................ [1669%]
........................................................................ [1672%]
........................................................................ [1676%]
............................................................[contention-diag] +3707s soak 36p/172t rss 13.6G pss 11.9G swap 1.4G majflt 674055 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.1G pss 11.5G, 8 descendant rss 0.2G pss 0.1G | host avail 36.6G/62.7G swapfree 41.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.14 cpu 24.52 | cgroup 12.8G/max oom_kill 0 | free scratch 296.3G/44688494i tmp 26.1G/985910i workspace 296.3G/44688494i | repeat-01 collected 26/26 workers (60629 items) tests 36330 done 3 failed | 22 in flight, oldest 399s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............ [1679%]
........................................................................ [1682%]
........................................................................ [1686%]
........................................................................ [1689%]
........................................................................ [1692%]
........................................................................ [1696%]
........................................................................ [1699%]
........................................................................ [1702%]
......[contention-diag] +3723s soak 33p/170t rss 13.7G pss 11.9G swap 1.4G majflt 685774 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.3G pss 11.7G, 5 descendant rss 0.0G pss 0.0G | host avail 35.6G/62.7G swapfree 41.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.7 cpu 25.03 | cgroup 12.8G/max oom_kill 0 | free scratch 296.3G/44687129i tmp 26.1G/985910i workspace 296.3G/44687129i | repeat-01 collected 26/26 workers (60629 items) tests 36858 done 3 failed | 22 in flight, oldest 414s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.................................................................. [1706%]
........................................................................ [1709%]
........................................................................ [1712%]
..................................[contention-diag] +3738s soak 33p/174t rss 13.9G pss 12.2G swap 1.3G majflt 695576 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 11.8G, 5 descendant rss 0.2G pss 0.1G | host avail 36.1G/62.7G swapfree 41.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.43 cpu 29.33 | cgroup 13.1G/max oom_kill 0 | free scratch 296.3G/44686029i tmp 26.1G/985910i workspace 296.3G/44686029i | repeat-01 collected 26/26 workers (60629 items) tests 37112 done 3 failed | 24 in flight, oldest 430s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...................................... [1716%]
........................................................................ [1719%]
........................................................................ [1722%]
......................................................................s. [1726%]
........................................................................ [1729%]
........................................................................ [1732%]
............................................[contention-diag] +3754s soak 32p/170t rss 14.1G pss 12.3G swap 1.3G majflt 695782 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.5G pss 11.9G, 4 descendant rss 0.2G pss 0.2G | host avail 34.2G/62.7G swapfree 41.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.03 cpu 24.52 | cgroup 13.2G/max oom_kill 0 | free scratch 296.3G/44684853i tmp 26.1G/985910i workspace 296.3G/44684853i | scratch used 0.4G in 67114 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 37503 done 3 failed | 23 in flight, oldest 445s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1735%]
.............................................F[contention-failure] call tests/test_output.py::test_provider_timer_thread_starts_before_live_enter: def test_provider_timer_thread_starts_before_live_enter() -> None:
        """The named timer thread exists before Live takes stdout."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        seen_during_enter: list[threading.Thread] = []
        original_enter = Live.__enter__
    
        def tracking_enter(self: Live) -> Live:
            seen_during_enter.extend(_provider_timer_threads(existing_thread_ids))
            return original_enter(self)
    
        with (
            patch.object(Live, "__enter__", tracking_enter),
            patch("sase.output.time.sleep", return_value=None),
            provider_timer("Short operation"),
        ):
>           _wait_for_provider_timer_thread(existing_thread_ids)

tests/test_output.py:148: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {139921494890176, 139921511675584, 139921830438592, 139922072655552, 139922565363584}

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
.......................... [1739%]
........................................................................ [1742%]
........................................................................ [1745%]
........................................................................ [1749%]
........................................................................ [1752%]
..................................................[contention-diag] +3771s soak 33p/176t rss 14.1G pss 12.3G swap 1.3G majflt 695970 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.5G pss 11.9G, 5 descendant rss 0.2G pss 0.2G | host avail 34.5G/62.7G swapfree 41.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.36 cpu 24.97 | cgroup 13.2G/max oom_kill 0 | free scratch 296.3G/44683062i tmp 26.1G/985909i workspace 296.3G/44683062i | repeat-01 collected 26/26 workers (60629 items) tests 37958 done 4 failed | 24 in flight, oldest 462s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
...................... [1755%]
........................................................................ [1759%]
........................................................................ [1762%]
........................................................................ [1765%]
........................................................................ [1769%]
......................................s................................. [1772%]
........................................................................ [1775%]
.......[contention-diag] +3786s soak 37p/185t rss 14.2G pss 12.4G swap 1.3G majflt 696414 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 9 descendant rss 0.3G pss 0.3G | host avail 33.4G/62.7G swapfree 41.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.38 cpu 23.27 | cgroup 13.4G/max oom_kill 0 | free scratch 296.3G/44681325i tmp 26.1G/985906i workspace 296.3G/44681325i | repeat-01 collected 26/26 workers (60629 items) tests 38431 done 4 failed | 24 in flight, oldest 478s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
................................................................. [1779%]
........................................................................ [1782%]
........................................................................ [1785%]
..............................................[contention-diag] +3802s soak 37p/185t rss 14.4G pss 12.6G swap 1.3G majflt 696980 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 9 descendant rss 0.4G pss 0.4G | host avail 33.7G/62.7G swapfree 41.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.32 cpu 19.9 | cgroup 13.5G/max oom_kill 0 | free scratch 296.3G/44681115i tmp 26.1G/985906i workspace 296.3G/44681115i | repeat-01 collected 26/26 workers (60629 items) tests 38696 done 4 failed | 24 in flight, oldest 379s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......................... [1789%]
........................................................................ [1792%]
........................................[contention-diag] +3817s soak 34p/182t rss 14.2G pss 12.5G swap 1.3G majflt 697278 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 6 descendant rss 0.3G pss 0.3G | host avail 34.4G/62.7G swapfree 42.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.57 cpu 20.25 | cgroup 13.4G/max oom_kill 0 | free scratch 296.3G/44680455i tmp 26.1G/985906i workspace 296.3G/44680455i | repeat-01 collected 26/26 workers (60629 items) tests 38842 done 4 failed | 24 in flight, oldest 394s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................ [1795%]
........................................................................ [1799%]
........................................................................ [1802%]
.................................[contention-diag] +3833s soak 37p/192t rss 14.5G pss 12.6G swap 1.3G majflt 697417 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 9 descendant rss 0.6G pss 0.4G | host avail 32.9G/62.7G swapfree 42.3G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 3.77 cpu 18.64 | cgroup 13.6G/max oom_kill 0 | free scratch 296.3G/44679473i tmp 26.1G/985902i workspace 296.3G/44679473i | repeat-01 collected 26/26 workers (60629 items) tests 39053 done 4 failed | 24 in flight, oldest 410s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
....................................... [1805%]
........................................................................ [1809%]
........................................................................ [1812%]
........................................................................ [1815%]
........................................................................ [1819%]
........................................................................ [1822%]
........................................................................ [1825%]
...................................................[contention-diag] +3848s soak 36p/182t rss 14.4G pss 12.5G swap 1.3G majflt 697699 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 8 descendant rss 0.4G pss 0.3G | host avail 33.3G/62.7G swapfree 42.4G/64.0G oom_kill +0 | psi10 mem 0.56/0.56 io 4.59 cpu 18.82 | cgroup 13.5G/max oom_kill 0 | free scratch 296.2G/44678691i tmp 26.1G/985905i workspace 296.2G/44678691i | repeat-01 collected 26/26 workers (60629 items) tests 39557 done 4 failed | 24 in flight, oldest 425s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
..................... [1829%]
........................................................................ [1832%]
........................................................................ [1835%]
........................................................................ [1839%]
........................................................................ [1842%]
........................................[contention-diag] +3863s soak 38p/186t rss 14.4G pss 12.6G swap 1.3G majflt 697803 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 10 descendant rss 0.5G pss 0.4G | host avail 33.3G/62.7G swapfree 42.5G/64.0G oom_kill +0 | psi10 mem 0.11/0.11 io 5.25 cpu 20.1 | cgroup 13.7G/max oom_kill 0 | free scratch 296.2G/44677250i tmp 26.1G/985905i workspace 296.2G/44677250i | repeat-01 collected 26/26 workers (60629 items) tests 39925 done 4 failed | 24 in flight, oldest 441s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................ [1845%]
........................................................................ [1849%]
........................................................................ [1852%]
............................................................[contention-diag] +3879s soak 41p/188t rss 14.3G pss 12.4G swap 1.3G majflt 698139 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 13 descendant rss 0.3G pss 0.2G | host avail 31.6G/62.7G swapfree 42.7G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 3.84 cpu 18.93 | cgroup 14.1G/max oom_kill 0 | free scratch 296.2G/44676611i tmp 26.1G/985905i workspace 296.2G/44676611i | scratch used 0.4G in 79199 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 40138 done 4 failed | 24 in flight, oldest 51s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
............ [1855%]
........................................................................ [1859%]
........................................................................ [1862%]
...............................s........................................ [1865%]
............................................[contention-diag] +3896s soak 38p/186t rss 14.3G pss 12.5G swap 1.3G majflt 698565 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 10 descendant rss 0.3G pss 0.2G | host avail 32.0G/62.7G swapfree 42.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.78 cpu 18.33 | cgroup 14.2G/max oom_kill 0 | free scratch 295.9G/44675499i tmp 26.1G/985905i workspace 295.9G/44675499i | repeat-01 collected 26/26 workers (60629 items) tests 40423 done 4 failed | 23 in flight, oldest 68s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
............................ [1869%]
........................................................................ [1872%]
........................................................................ [1875%]
........................................................................ [1878%]
.......................................[contention-diag] +3912s soak 43p/186t rss 14.4G pss 12.5G swap 1.2G majflt 698702 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.7G pss 12.0G, 15 descendant rss 0.4G pss 0.3G | host avail 32.0G/62.7G swapfree 42.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.92 cpu 17.47 | cgroup 14.3G/max oom_kill 0 | free scratch 295.6G/44674207i tmp 26.1G/985905i workspace 295.6G/44674207i | repeat-01 collected 26/26 workers (60629 items) tests 40718 done 4 failed | 24 in flight, oldest 83s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
................................. [1882%]
........................................................................ [1885%]
........................................................................ [1888%]
...................................................................[contention-diag] +3927s soak 40p/181t rss 14.5G pss 12.6G swap 1.2G majflt 698857 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.7G pss 12.0G, 12 descendant rss 0.5G pss 0.4G | host avail 29.6G/62.7G swapfree 42.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.67 cpu 15.38 | cgroup 13.9G/max oom_kill 0 | free scratch 296.2G/44673525i tmp 26.1G/985903i workspace 296.2G/44673525i | repeat-01 collected 26/26 workers (60629 items) tests 40958 done 4 failed | 23 in flight, oldest 99s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
..... [1892%]
........................................................................ [1895%]
........................................................................ [1898%]
........................................................................ [1902%]
........................................................................ [1905%]
........................................................................ [1908%]
........................................................................ [1912%]
........................................................................ [1915%]
.......[contention-diag] +3943s soak 35p/175t rss 14.3G pss 12.5G swap 1.2G majflt 699209 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.7G pss 12.0G, 7 descendant rss 0.2G pss 0.2G | host avail 31.0G/62.7G swapfree 42.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.78 cpu 16.39 | cgroup 13.7G/max oom_kill 0 | free scratch 296.2G/44671236i tmp 26.1G/985902i workspace 296.2G/44671236i | repeat-01 collected 26/26 workers (60629 items) tests 41456 done 4 failed | 23 in flight, oldest 114s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
................................................................. [1918%]
........................................................................ [1922%]
........................................................................ [1925%]
........................................................................ [1928%]
........................................................................ [1932%]
.....................................[contention-diag] +3958s soak 36p/174t rss 14.5G pss 12.7G swap 1.2G majflt 699392 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.7G pss 12.0G, 8 descendant rss 0.4G pss 0.4G | host avail 29.5G/62.7G swapfree 42.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.62 cpu 16.71 | cgroup 13.8G/max oom_kill 0 | free scratch 296.2G/44669504i tmp 26.1G/985902i workspace 296.2G/44669504i | repeat-01 collected 26/26 workers (60629 items) tests 41862 done 4 failed | 24 in flight, oldest 130s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
................................... [1935%]
........................................................................ [1938%]
........................................................................ [1942%]
........................................................................ [1945%]
.................................................................[contention-diag] +3974s soak 38p/178t rss 14.4G pss 12.6G swap 1.2G majflt 699650 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.7G pss 12.0G, 10 descendant rss 0.3G pss 0.3G | host avail 29.7G/62.7G swapfree 42.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.98 cpu 16.62 | cgroup 13.8G/max oom_kill 0 | free scratch 296.7G/44677839i tmp 26.1G/985902i workspace 296.7G/44677839i | repeat-01 collected 26/26 workers (60629 items) tests 42177 done 4 failed | 24 in flight, oldest 145s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
....... [1948%]
........................................................................ [1952%]
........................................................................ [1955%]
........................................................................ [1958%]
........................................................................ [1962%]
........................................................................ [1965%]
.......................................................[contention-diag] +3989s soak 43p/186t rss 14.7G pss 12.8G swap 1.2G majflt 699821 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.7G pss 12.0G, 15 descendant rss 0.6G pss 0.5G | host avail 31.5G/62.7G swapfree 42.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.95 cpu 20.08 | cgroup 14.0G/max oom_kill 0 | free scratch 296.6G/44671639i tmp 26.1G/985889i workspace 296.6G/44671639i | repeat-01 collected 26/26 workers (60629 items) tests 42597 done 4 failed | 23 in flight, oldest 161s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 8 hazardous kill call(s)
................. [1968%]
........................................................................ [1972%]
........................................................................ [1975%]
........................................................................ [1978%]
........................................................................ [1982%]
........................................................................ [1985%]
........................................................................ [1988%]
........................................................................ [1992%]
.......[contention-diag] +4004s soak 39p/186t rss 14.6G pss 12.8G swap 1.2G majflt 700392 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.8G pss 12.0G, 11 descendant rss 0.5G pss 0.4G | host avail 30.1G/62.7G swapfree 42.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.15 cpu 19.01 | cgroup 14.0G/max oom_kill 0 | free scratch 296.6G/44670281i tmp 26.1G/985889i workspace 296.6G/44670281i | scratch used 0.5G in 86327 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 43072 done 4 failed | 24 in flight, oldest 176s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
................................................................. [1995%]
........................................................................ [1998%]
........................................................................ [2002%]
........................................................................ [2005%]
...............................................[contention-diag] +4022s soak 40p/185t rss 14.7G pss 12.8G swap 1.2G majflt 700642 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.8G pss 12.1G, 12 descendant rss 0.6G pss 0.5G | host avail 28.0G/62.7G swapfree 42.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.39 cpu 17.39 | cgroup 14.1G/max oom_kill 0 | free scratch 296.6G/44668641i tmp 26.1G/985889i workspace 296.6G/44668641i | repeat-01 collected 26/26 workers (60629 items) tests 43461 done 4 failed | 24 in flight, oldest 194s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
......................... [2008%]
........................................................................ [2012%]
........................................................................ [2015%]
.............................................................[contention-diag] +4037s soak 38p/192t rss 14.8G pss 12.9G swap 1.2G majflt 700994 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.8G pss 12.1G, 10 descendant rss 0.6G pss 0.5G | host avail 29.6G/62.7G swapfree 42.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.53 cpu 17.08 | cgroup 14.3G/max oom_kill 0 | free scratch 296.4G/44667613i tmp 26.1G/985889i workspace 296.4G/44667613i | repeat-01 collected 26/26 workers (60629 items) tests 43692 done 4 failed | 24 in flight, oldest 209s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
........... [2018%]
........................................................................ [2021%]
........................................................................ [2025%]
........................................................................ [2028%]
.........[contention-diag] +4053s soak 42p/194t rss 14.7G pss 12.7G swap 1.2G majflt 701310 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.8G pss 11.8G, 14 descendant rss 0.6G pss 0.5G | host avail 27.6G/62.7G swapfree 42.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.06 cpu 16.28 | cgroup 14.2G/max oom_kill 0 | free scratch 296.5G/44665523i tmp 26.1G/985889i workspace 296.5G/44665523i | repeat-01 collected 26/26 workers (60629 items) tests 43927 done 4 failed | 24 in flight, oldest 225s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
............................................................... [2031%]
........................................................................ [2035%]
........................................................................ [2038%]
........................................[contention-diag] +4068s soak 36p/184t rss 14.9G pss 13.1G swap 1.2G majflt 701406 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.8G pss 12.1G, 8 descendant rss 0.7G pss 0.7G | host avail 27.8G/62.7G swapfree 42.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.27 cpu 17.41 | cgroup 14.4G/max oom_kill 0 | free scratch 296.6G/44671491i tmp 26.1G/985889i workspace 296.6G/44671491i | repeat-01 collected 26/26 workers (60629 items) tests 44164 done 4 failed | 24 in flight, oldest 240s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
................................ [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
........................................................................ [2051%]
........................................................................ [2055%]
........................................................................ [2058%]
........................................................................ [2061%]
........................................................................ [2065%]
.........[contention-diag] +4084s soak 36p/183t rss 14.8G pss 13.0G swap 1.2G majflt 701873 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.8G pss 12.1G, 8 descendant rss 0.6G pss 0.6G | host avail 28.4G/62.7G swapfree 43.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.43 cpu 18.78 | cgroup 14.4G/max oom_kill 0 | free scratch 296.4G/44667506i tmp 26.1G/985888i workspace 296.4G/44667506i | repeat-01 collected 26/26 workers (60629 items) tests 44698 done 4 failed | 22 in flight, oldest 255s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
............................................................... [2068%]
........................................................................ [2071%]
........................................................................ [2075%]
........................................................................ [2078%]
........................................................................ [2081%]
........................................................................ [2085%]
...................................[contention-diag] +4099s soak 36p/189t rss 14.8G pss 12.9G swap 1.2G majflt 702138 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 8 descendant rss 0.8G pss 0.7G | host avail 30.8G/62.7G swapfree 43.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.09 cpu 14.68 | cgroup 14.4G/max oom_kill 0 | free scratch 296.1G/44665735i tmp 26.1G/985887i workspace 296.1G/44665735i | repeat-01 collected 26/26 workers (60629 items) tests 45174 done 4 failed | 22 in flight, oldest 271s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
..................................... [2088%]
........................................................................ [2091%]
........................................................................ [2095%]
........................................................................ [2098%]
..........[contention-diag] +4115s soak 41p/194t rss 14.9G pss 13.0G swap 1.2G majflt 702253 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 13 descendant rss 0.9G pss 0.8G | host avail 31.5G/62.7G swapfree 43.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.08 cpu 15.6 | cgroup 14.5G/max oom_kill 0 | free scratch 295.6G/44659595i tmp 26.1G/985886i workspace 295.6G/44659595i | repeat-01 collected 26/26 workers (60629 items) tests 45442 done 4 failed | 22 in flight, oldest 286s gw15 tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint | 9 hazardous kill call(s)
.............................................................. [2101%]
........................................................................ [2105%]
........................................................................ [2108%]
........................................................................ [2111%]
.......................s................................................ [2115%]
........................................................................ [2118%]
........................................................................ [2121%]
....[contention-diag] +4130s soak 34p/188t rss 14.6G pss 12.8G swap 1.2G majflt 702673 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 6 descendant rss 0.6G pss 0.6G | host avail 30.8G/62.7G swapfree 43.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.8 cpu 20.12 | cgroup 14.2G/max oom_kill 0 | free scratch 295.5G/44657676i tmp 26.1G/985888i workspace 295.5G/44657676i | scratch used 0.5G in 96636 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 45870 done 4 failed | 22 in flight, oldest 225s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.................................................................... [2125%]
........................................................................ [2128%]
........................................................................ [2131%]
........................................................................ [2135%]
........................................................................ [2138%]
........................................................................ [2141%]
........................................................................ [2145%]
........................................................................ [2148%]
..................................................[contention-diag] +4148s soak 35p/180t rss 14.7G pss 12.9G swap 1.2G majflt 702911 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.6G pss 11.9G, 7 descendant rss 0.7G pss 0.6G | host avail 29.1G/62.7G swapfree 43.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.42 cpu 17.77 | cgroup 14.4G/max oom_kill 0 | free scratch 295.1G/44653935i tmp 26.1G/985888i workspace 295.1G/44653935i | repeat-01 collected 26/26 workers (60629 items) tests 46557 done 4 failed | 21 in flight, oldest 243s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
...................... [2151%]
........................................................................ [2155%]
........................................................................ [2158%]
........................................................................ [2161%]
........................................................................ [2164%]
........................................................................ [2168%]
.........................[contention-diag] +4163s soak 37p/194t rss 14.9G pss 13.0G swap 1.2G majflt 703042 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 11.9G, 9 descendant rss 0.8G pss 0.7G | host avail 32.4G/62.7G swapfree 43.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.6 cpu 21.02 | cgroup 14.5G/max oom_kill 0 | free scratch 295.1G/44653174i tmp 26.1G/985887i workspace 295.1G/44653174i | repeat-01 collected 26/26 workers (60629 items) tests 46967 done 4 failed | 22 in flight, oldest 258s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................... [2171%]
........................................................................ [2174%]
........................................................................ [2178%]
........................................................................ [2181%]
........................................................................ [2184%]
........................................................................ [2188%]
........................................................................ [2191%]
........................................................................ [2194%]
........................................................................ [2198%]
..........[contention-diag] +4178s soak 38p/177t rss 15.1G pss 13.1G swap 1.2G majflt 703155 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 11.9G, 10 descendant rss 1.0G pss 0.9G | host avail 32.2G/62.7G swapfree 43.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.57 cpu 27.79 | cgroup 14.7G/max oom_kill 0 | free scratch 295.0G/44651370i tmp 26.1G/985887i workspace 295.0G/44651370i | repeat-01 collected 26/26 workers (60629 items) tests 47597 done 4 failed | 21 in flight, oldest 274s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................................................. [2201%]
........................................................................ [2204%]
........................................................................ [2208%]
........................................................................ [2211%]
...........................................[contention-diag] +4194s soak 44p/205t rss 14.9G pss 13.0G swap 1.2G majflt 703450 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 11.9G, 16 descendant rss 0.8G pss 0.7G | host avail 31.7G/62.7G swapfree 43.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 28.43 | cgroup 14.6G/max oom_kill 0 | free scratch 295.0G/44648578i tmp 26.1G/985887i workspace 295.0G/44648578i | repeat-01 collected 26/26 workers (60629 items) tests 47914 done 4 failed | 22 in flight, oldest 289s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................. [2214%]
........................................................................ [2218%]
........................................................................ [2221%]
........................................................................ [2224%]
........[contention-diag] +4209s soak 40p/193t rss 15.0G pss 12.9G swap 1.2G majflt 703499 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 11.7G, 12 descendant rss 0.9G pss 0.8G | host avail 29.5G/62.7G swapfree 43.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 26.98 | cgroup 14.7G/max oom_kill 0 | free scratch 295.0G/44648179i tmp 26.1G/985887i workspace 295.0G/44648179i | repeat-01 collected 26/26 workers (60629 items) tests 48162 done 4 failed | 22 in flight, oldest 305s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................................ [2228%]
........................................................................ [2231%]
........................................................................ [2234%]
........................................................................ [2238%]
........................................................................ [2241%]
........................................................................ [2244%]
........................................................................ [2248%]
...............................[contention-diag] +4224s soak 35p/175t rss 15.0G pss 13.1G swap 1.2G majflt 704413 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 11.9G, 7 descendant rss 0.9G pss 0.8G | host avail 31.8G/62.7G swapfree 43.4G/64.0G oom_kill +0 | psi10 mem 0.49/0.49 io 1.25 cpu 30.44 | cgroup 14.8G/max oom_kill 0 | free scratch 295.0G/44646406i tmp 26.1G/985887i workspace 295.0G/44646406i | repeat-01 collected 26/26 workers (60629 items) tests 48669 done 4 failed | 19 in flight, oldest 320s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
......................................... [2251%]
........................................................................ [2254%]
........................................................................ [2258%]
........................................................................ [2261%]
......................[contention-diag] +4240s soak 39p/178t rss 15.3G pss 13.4G swap 1.2G majflt 704484 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.0G, 11 descendant rss 1.2G pss 1.1G | host avail 31.0G/62.7G swapfree 43.4G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 0.35 cpu 26.56 | cgroup 15.2G/max oom_kill 0 | free scratch 295.0G/44646555i tmp 26.1G/985886i workspace 295.0G/44646555i | repeat-01 collected 26/26 workers (60629 items) tests 48981 done 4 failed | 20 in flight, oldest 335s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.................................................. [2264%]
........................................................................ [2268%]
.............................................[contention-diag] +4255s soak 38p/178t rss 15.3G pss 13.4G swap 1.2G majflt 704541 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.0G, 10 descendant rss 1.2G pss 1.1G | host avail 29.7G/62.7G swapfree 43.4G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.26 cpu 22.95 | cgroup 15.2G/max oom_kill 0 | free scratch 295.0G/44646804i tmp 26.1G/985886i workspace 295.0G/44646804i | scratch used 0.6G in 107097 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 49129 done 4 failed | 19 in flight, oldest 351s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................... [2271%]
........................................................................ [2274%]
........................................................................ [2278%]
................[contention-diag] +4273s soak 37p/182t rss 15.1G pss 13.3G swap 1.1G majflt 705271 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.0G, 9 descendant rss 1.0G pss 0.9G | host avail 28.5G/62.7G swapfree 43.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.34 cpu 19.11 | cgroup 15.2G/max oom_kill 0 | free scratch 295.0G/44646319i tmp 26.1G/985886i workspace 295.0G/44646319i | repeat-01 collected 26/26 workers (60629 items) tests 49333 done 4 failed | 19 in flight, oldest 368s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................................ [2281%]
........................................................................ [2284%]
...........[contention-diag] +4288s soak 37p/188t rss 15.2G pss 13.3G swap 1.1G majflt 705308 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.8G pss 12.0G, 9 descendant rss 1.1G pss 1.0G | host avail 31.7G/62.7G swapfree 43.4G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 0.18 cpu 20.97 | cgroup 15.3G/max oom_kill 0 | free scratch 295.0G/44645865i tmp 26.1G/985883i workspace 295.0G/44645865i | repeat-01 collected 26/26 workers (60629 items) tests 49475 done 4 failed | 19 in flight, oldest 384s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................................. [2288%]
........................................................................ [2291%]
..........................................................[contention-diag] +4304s soak 37p/181t rss 15.2G pss 13.3G swap 1.1G majflt 705330 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.8G pss 12.0G, 9 descendant rss 1.1G pss 1.0G | host avail 30.6G/62.7G swapfree 43.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 21.05 | cgroup 15.4G/max oom_kill 0 | free scratch 295.0G/44646837i tmp 26.1G/985886i workspace 295.0G/44646837i | repeat-01 collected 26/26 workers (60629 items) tests 49661 done 4 failed | 19 in flight, oldest 399s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............. [2294%]
........................................................................ [2298%]
........................................................................ [2301%]
.........................................[contention-diag] +4319s soak 37p/174t rss 15.3G pss 13.4G swap 1.1G majflt 705572 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.8G pss 12.0G, 9 descendant rss 1.1G pss 1.0G | host avail 30.2G/62.7G swapfree 43.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.61 | cgroup 15.5G/max oom_kill 0 | free scratch 295.0G/44646689i tmp 26.1G/985885i workspace 295.0G/44646689i | repeat-01 collected 26/26 workers (60629 items) tests 49854 done 4 failed | 18 in flight, oldest 414s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................... [2304%]
........................................................................ [2307%]
........................................................................ [2311%]
........................................................................ [2314%]
........................................................................ [2317%]
........................................................................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
.................[contention-diag] +4334s soak 37p/175t rss 15.3G pss 13.4G swap 1.1G majflt 705666 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.8G pss 12.0G, 9 descendant rss 1.1G pss 1.0G | host avail 31.8G/62.7G swapfree 43.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 25.51 | cgroup 15.5G/max oom_kill 0 | free scratch 295.0G/44645275i tmp 26.1G/985885i workspace 295.0G/44645275i | repeat-01 collected 26/26 workers (60629 items) tests 50400 done 4 failed | 18 in flight, oldest 430s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....................................................... [2331%]
........................................................................ [2334%]
........................................................................ [2337%]
........................................................................ [2341%]
........................................................................ [2344%]
........................................................................ [2347%]
...........................................[contention-diag] +4350s soak 39p/185t rss 15.4G pss 13.5G swap 1.1G majflt 706002 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.0G, 11 descendant rss 1.3G pss 1.2G | host avail 30.4G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 25.12 | cgroup 15.6G/max oom_kill 0 | free scratch 295.0G/44643614i tmp 26.1G/985885i workspace 295.0G/44643614i | repeat-01 collected 26/26 workers (60629 items) tests 50864 done 4 failed | 18 in flight, oldest 445s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................. [2351%]
........................................................................ [2354%]
........................................................................ [2357%]
........................................................................ [2361%]
......[contention-diag] +4365s soak 44p/197t rss 15.8G pss 13.8G swap 1.1G majflt 706304 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.0G, 16 descendant rss 1.6G pss 1.5G | host avail 30.1G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.23 | cgroup 16.0G/max oom_kill 0 | free scratch 295.0G/44642609i tmp 26.1G/985885i workspace 295.0G/44642609i | repeat-01 collected 26/26 workers (60629 items) tests 51121 done 4 failed | 18 in flight, oldest 461s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.................................................................. [2364%]
........................................................................ [2367%]
........................................................................ [2371%]
........................................................................ [2374%]
........................................................................ [2377%]
........................................................................ [2381%]
..........................[contention-diag] +4381s soak 42p/189t rss 15.5G pss 13.6G swap 1.1G majflt 706555 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.0G, 14 descendant rss 1.3G pss 1.2G | host avail 29.5G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 19.14 | cgroup 15.7G/max oom_kill 0 | free scratch 294.7G/44640148i tmp 26.1G/985885i workspace 294.7G/44640148i | scratch used 0.6G in 113195 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 51549 done 4 failed | 18 in flight, oldest 476s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................................. [2384%]
........................................................................ [2387%]
........................................................................ [2391%]
........................................................................ [2394%]
........................................................................ [2397%]
........................................................................ [2401%]
........................................................................ [2404%]
.......[contention-diag] +4398s soak 39p/184t rss 15.5G pss 13.6G swap 1.1G majflt 706615 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.0G, 11 descendant rss 1.3G pss 1.2G | host avail 28.5G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 18.19 | cgroup 15.8G/max oom_kill 0 | free scratch 294.3G/44637450i tmp 26.1G/985885i workspace 294.3G/44637450i | repeat-01 collected 26/26 workers (60629 items) tests 52051 done 4 failed | 18 in flight, oldest 493s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................................. [2407%]
........................................................................ [2411%]
........................................................................ [2414%]
........................................................................ [2417%]
........................................................................ [2421%]
........................................................................ [2424%]
.........................[contention-diag] +4414s soak 38p/181t rss 15.4G pss 13.6G swap 1.1G majflt 706948 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.0G, 10 descendant rss 1.2G pss 1.1G | host avail 28.3G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 19.49 | cgroup 15.8G/max oom_kill 0 | free scratch 294.3G/44635923i tmp 26.1G/985885i workspace 294.3G/44635923i | repeat-01 collected 26/26 workers (60629 items) tests 52497 done 4 failed | 18 in flight, oldest 509s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................... [2427%]
........................................................................ [2431%]
........................................................................ [2434%]
..........................s............................................. [2437%]
........................................................................ [2441%]
........................................................................ [2444%]
........................................................................ [2447%]
......................................[contention-diag] +4429s soak 40p/176t rss 15.6G pss 13.6G swap 1.1G majflt 707223 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.1G, 12 descendant rss 1.3G pss 1.2G | host avail 27.4G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.98 cpu 19.78 | cgroup 15.9G/max oom_kill 0 | free scratch 294.3G/44634478i tmp 26.1G/985885i workspace 294.3G/44634478i | repeat-01 collected 26/26 workers (60629 items) tests 52998 done 4 failed | 18 in flight, oldest 525s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................................. [2450%]
........................................................................ [2454%]
........................................................................ [2457%]
........................................................................ [2460%]
........................................................................ [2464%]
........................................................................ [2467%]
........................................................................ [2470%]
......................................[contention-diag] +4445s soak 39p/172t rss 15.7G pss 13.8G swap 1.1G majflt 707285 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.1G, 11 descendant rss 1.5G pss 1.4G | host avail 27.4G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.77 cpu 18.73 | cgroup 16.0G/max oom_kill 0 | free scratch 294.3G/44633051i tmp 26.1G/985885i workspace 294.3G/44633051i | repeat-01 collected 26/26 workers (60629 items) tests 53506 done 4 failed | 18 in flight, oldest 540s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................................. [2474%]
........................................................................ [2477%]
........................................................................ [2480%]
........................................................................ [2484%]
........................................................................ [2487%]
........................................................................ [2490%]
........................................................................ [2494%]
..............................................................[contention-diag] +4460s soak 39p/171t rss 15.7G pss 13.7G swap 1.1G majflt 708167 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 11 descendant rss 1.4G pss 1.3G | host avail 25.6G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.44/0.24 io 0.42 cpu 20.17 | cgroup 16.0G/max oom_kill 0 | free scratch 294.2G/44632174i tmp 26.1G/985885i workspace 294.2G/44632174i | repeat-01 collected 26/26 workers (60629 items) tests 54060 done 4 failed | 17 in flight, oldest 556s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.......... [2497%]
........................................................................ [2500%]
........................................................................ [2504%]
........................................................................ [2507%]
........................................................................ [2510%]
........................................................................ [2514%]
........................................................................ [2517%]
........................................................................ [2520%]
....................[contention-diag] +4476s soak 39p/173t rss 15.7G pss 13.7G swap 1.1G majflt 708390 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 11 descendant rss 1.4G pss 1.2G | host avail 24.2G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.08/0.04 io 0.08 cpu 19.76 | cgroup 15.9G/max oom_kill 0 | free scratch 294.0G/44631699i tmp 26.1G/985885i workspace 294.0G/44631699i | repeat-01 collected 26/26 workers (60629 items) tests 54582 done 4 failed | 16 in flight, oldest 571s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................................................... [2524%]
........................................................................ [2527%]
........................................................................ [2530%]
........................................................................ [2534%]
........................................................................ [2537%]
........................................................................ [2540%]
........................................................................ [2544%]
......................................................[contention-diag] +4491s soak 37p/161t rss 15.6G pss 13.7G swap 1.1G majflt 708571 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 9 descendant rss 1.3G pss 1.2G | host avail 28.3G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 0.66 cpu 23.08 | cgroup 16.0G/max oom_kill 0 | free scratch 293.7G/44630932i tmp 26.1G/985885i workspace 293.7G/44630932i | repeat-01 collected 26/26 workers (60629 items) tests 55117 done 4 failed | 14 in flight, oldest 587s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.................. [2547%]
........................................................................ [2550%]
........................................................................ [2554%]
........................................................................ [2557%]
........................................................................ [2560%]
........................................................................ [2564%]
........................................................................ [2567%]
........................................................................ [2570%]
........................................................................ [2574%]
.......................................[contention-diag] +4507s soak 39p/187t rss 15.9G pss 13.9G swap 1.1G majflt 708643 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 11 descendant rss 1.5G pss 1.4G | host avail 27.9G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.7 cpu 22.69 | cgroup 16.2G/max oom_kill 0 | free scratch 293.5G/44629330i tmp 26.1G/985882i workspace 293.5G/44629330i | scratch used 0.7G in 122730 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 55743 done 4 failed | 15 in flight, oldest 602s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................. [2577%]
........................................................................ [2580%]
........................................................................ [2584%]
........................................................................ [2587%]
........................................................................ [2590%]
........................................................................ [2593%]
............[contention-diag] +4524s soak 37p/169t rss 16.1G pss 14.1G swap 1.0G majflt 708807 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 9 descendant rss 1.8G pss 1.7G | host avail 28.7G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.06 cpu 25.25 | cgroup 16.4G/max oom_kill 0 | free scratch 293.5G/44628790i tmp 26.1G/985882i workspace 293.5G/44628790i | repeat-01 collected 26/26 workers (60629 items) tests 56169 done 4 failed | 14 in flight, oldest 619s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
............................................................ [2597%]
........................................................................ [2600%]
........................................................................ [2603%]
........................................................................ [2607%]
........................................................................ [2610%]
........................................................................ [2613%]
........................................................................ [2617%]
........................................................................ [2620%]
.............................................[contention-diag] +4539s soak 37p/168t rss 15.8G pss 13.8G swap 1.1G majflt 708889 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 9 descendant rss 1.4G pss 1.3G | host avail 28.3G/62.7G swapfree 43.5G/64.0G oom_kill +0 | psi10 mem 0.84/0.84 io 0.65 cpu 23.05 | cgroup 16.1G/max oom_kill 0 | free scratch 293.5G/44626955i tmp 26.1G/985882i workspace 293.5G/44626955i | repeat-01 collected 26/26 workers (60629 items) tests 56775 done 4 failed | 13 in flight, oldest 635s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
........................... [2623%]
........................................................................ [2627%]
........................................................................ [2630%]
........................................................................ [2633%]
........................................................................ [2637%]
..................s..................................................... [2640%]
........................................................................ [2643%]
........................................................................ [2647%]
........................................................................ [2650%]
........................................................................ [2653%]
.........................[contention-diag] +4555s soak 44p/174t rss 14.6G pss 12.7G swap 1.1G majflt 709014 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 16 descendant rss 0.3G pss 0.2G | host avail 27.7G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.17/0.17 io 0.17 cpu 21.56 | cgroup 15.0G/max oom_kill 0 | free scratch 293.4G/44624906i tmp 26.1G/985882i workspace 293.4G/44624905i | repeat-01 collected 26/26 workers (60629 items) tests 57423 done 4 failed | 14 in flight, oldest 7s gw7 tests/test_suite_gate_scoped_integration.py::test_scoped_run_ignores_parent_shard_spec | 10 hazardous kill call(s)
............................................... [2657%]
........................................................................ [2660%]
........................................................................ [2663%]
........................................................................ [2667%]
..........[contention-diag] +4570s soak 42p/184t rss 15.1G pss 13.1G swap 1.0G majflt 709104 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 14 descendant rss 0.8G pss 0.6G | host avail 28.7G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.12 cpu 22.95 | cgroup 15.5G/max oom_kill 0 | free scratch 293.4G/44624537i tmp 26.1G/985882i workspace 293.4G/44624537i | repeat-01 collected 26/26 workers (60629 items) tests 57749 done 4 failed | 13 in flight, oldest 22s gw21 tests/test_keymaps_e2e.py::test_agents_prompt_input_ctrl_k_keeps_local_history_priority | 10 hazardous kill call(s)
.............................................................. [2670%]
........................................................................ [2673%]
........................................................................ [2677%]
..................................................[contention-diag] +4586s soak 40p/165t rss 14.9G pss 13.0G swap 1.0G majflt 709199 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 12 descendant rss 0.6G pss 0.5G | host avail 27.8G/62.7G swapfree 43.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 21.33 | cgroup 15.4G/max oom_kill 0 | free scratch 293.7G/44669279i tmp 26.1G/985882i workspace 293.7G/44669279i | repeat-01 collected 26/26 workers (60629 items) tests 57998 done 4 failed | 11 in flight, oldest 37s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
...................... [2680%]
........................................................................ [2683%]
........................................................................ [2687%]
...............................................[contention-diag] +4601s soak 41p/167t rss 14.6G pss 12.6G swap 1.0G majflt 709263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 13 descendant rss 0.2G pss 0.2G | host avail 28.3G/62.7G swapfree 43.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 25.8 | cgroup 15.0G/max oom_kill 0 | free scratch 294.1G/44738128i tmp 26.1G/985882i workspace 294.1G/44738128i | repeat-01 collected 26/26 workers (60629 items) tests 58207 done 4 failed | 11 in flight, oldest 52s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
......................... [2690%]
........................................................................ [2693%]
........................................................................ [2697%]
........................................................................ [2700%]
........................................................................ [2703%]
........................................................................ [2707%]
........................................................................ [2710%]
........................................................................ [2713%]
....[contention-diag] +4616s soak 33p/158t rss 14.5G pss 12.7G swap 1.0G majflt 709373 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 5 descendant rss 0.2G pss 0.2G | host avail 27.8G/62.7G swapfree 43.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 23.23 | cgroup 15.1G/max oom_kill 0 | free scratch 294.2G/44769930i tmp 26.1G/985882i workspace 294.2G/44769930i | repeat-01 collected 26/26 workers (60629 items) tests 58750 done 4 failed | 11 in flight, oldest 67s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
.................................................................... [2717%]
........................................................................ [2720%]
........................................................................ [2723%]
........................................................................ [2727%]
........................................................................ [2730%]
........................................................................ [2733%]
........................................................................ [2736%]
.......................................[contention-diag] +4632s soak 35p/157t rss 14.6G pss 12.7G swap 1.0G majflt 709598 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 7 descendant rss 0.2G pss 0.2G | host avail 27.3G/62.7G swapfree 44.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.46 cpu 19.98 | cgroup 15.2G/max oom_kill 0 | free scratch 294.3G/44788333i tmp 26.1G/985882i workspace 294.3G/44788333i | scratch used 0.2G in 28726 entries (truncated) | repeat-01 collected 26/26 workers (60629 items) tests 59249 done 4 failed | 8 in flight, oldest 83s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
................................. [2740%]
........................................................................ [2743%]
........................................................................ [2746%]
.....................................................................[contention-diag] +4649s soak 36p/157t rss 14.6G pss 12.7G swap 1.0G majflt 709643 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.1G, 8 descendant rss 0.2G pss 0.2G | host avail 25.8G/62.7G swapfree 44.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 14.72 | cgroup 15.2G/max oom_kill 0 | free scratch 294.3G/44788818i tmp 26.1G/985882i workspace 294.3G/44788818i | repeat-01 collected 26/26 workers (60629 items) tests 59541 done 4 failed | 6 in flight, oldest 81s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
... [2750%]
........................................................................ [2753%]
...............................................[contention-diag] +4665s soak 33p/158t rss 14.4G pss 12.5G swap 1.0G majflt 709937 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 14.0G pss 12.1G, 5 descendant rss 0.0G pss 0.0G | host avail 24.6G/62.7G swapfree 44.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 14.82 | cgroup 15.1G/max oom_kill 0 | free scratch 294.3G/44790110i tmp 26.1G/985882i workspace 294.3G/44790110i | repeat-01 collected 26/26 workers (60629 items) tests 59652 done 4 failed | 4 in flight, oldest 1s gw16 tests/test_provider_priority_indicator.py::test_single_peek_drives_both_routing_groups | 10 hazardous kill call(s)
......................... [2756%]
........................................................................ [2760%]
........................................................................ [2763%]
.......................................................................[contention-diag] +4680s soak 36p/158t rss 14.4G pss 12.5G swap 1.1G majflt 710480 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.0G, 8 descendant rss 0.1G pss 0.0G | host avail 19.9G/62.7G swapfree 44.0G/64.0G oom_kill +0 | psi10 mem 0.71/0.59 io 1.04 cpu 11.17 | cgroup 15.0G/max oom_kill 0 | free scratch 294.7G/44793021i tmp 26.1G/985882i workspace 294.7G/44793021i | repeat-01 collected 26/26 workers (60629 items) tests 59903 done 4 failed | 4 in flight, oldest 1s gw21 tests/test_plan_gate_capacity.py::test_epic_gate_selection_translates_capacity_into_runner_protocol | 10 hazardous kill call(s)
. [2766%]
.................................................ssss................... [2770%]
........................................................................ [2773%]
........................................................................ [2776%]
........................................................................ [2780%]
........................................................................ [2783%]
........................................................................ [2786%]
......[contention-diag] +4696s soak 32p/151t rss 14.3G pss 12.4G swap 1.1G majflt 710792 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.9G pss 12.0G, 4 descendant rss 0.0G pss 0.0G | host avail 23.4G/62.7G swapfree 44.2G/64.0G oom_kill +0 | psi10 mem 0.17/0.14 io 0.69 cpu 7.38 | cgroup 15.1G/max oom_kill 0 | free scratch 294.7G/44793057i tmp 26.1G/985877i workspace 294.7G/44793057i | repeat-01 collected 26/26 workers (60629 items) tests 60342 done 4 failed | 2 in flight, oldest 7s gw16 tests/tool/test_detach_watchdog.py::test_watchdog_reports_ended_join_monitor | 10 hazardous kill call(s)
.................................................................. [2790%]
........................................................................ [2793%]
........................................................................ [2796%]
........................................................................ [2800%]
.....                                                                    [100%][contention-diag] +4710s soak 32p/60t rss 0.5G pss 0.4G swap 0.1G majflt 715972 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 0.0G pss 0.0G, 4 descendant rss 0.0G pss 0.0G | host avail 25.1G/62.7G swapfree 44.7G/64.0G oom_kill +0 | psi10 mem 4.51/0.02 io 0.14 cpu 11.02 | cgroup 13.7G/max oom_kill 0 | free scratch 294.7G/44793815i tmp 26.1G/985882i workspace 294.7G/44793815i | repeat-01 collected 26/26 workers (60629 items) tests 60588 done 4 failed | 10 hazardous kill call(s)


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
________ test_group_cycle_is_view_sensitive_and_projects_reuses_result _________
[gw19] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f705663eba0>

    async def test_group_cycle_is_view_sensitive_and_projects_reuses_result(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        calls: list[tuple[StatisticsView, StatsRange, str | None, str | None]] = []
        _patch_center(monkeypatch, calls)
    
        async with AcePage() as page:
            _, pane = await _open_statistics(page)
    
            grouping_views = {"projects", "macros", "perf", "footprint"}
            for view in VIEW_ORDER:
                pane._set_view(view)
                await page.pause()
                group_scope = pane.query_one("#statistics-scope-group", Static)
                assert group_scope.display is (view in grouping_views)
                if view in grouping_views:
                    continue
                pane.action_cycle_group()
                await page.pause()
                assert pane._projects_group_by == "project"
                assert pane._perf_group_by == "subsystem"
    
            pane._set_view("perf")
            await page.wait_for(
                lambda _state: (
                    pane._last_result is not None
                    and pane._last_result.perf is not None
                    and not pane._loading
                    and (
                        pane._load_debouncer is None or not pane._load_debouncer.is_pending
                    )
                )
            )
            pane._set_view("projects")
            await _wait_statistics_settled(page, pane)
            cached_calls = len(calls)
            pane.action_cycle_group()
            await page.pause()
    
            assert pane._projects_group_by == "repo"
            assert len(calls) == cached_calls
            assert "Projects · By Repo" in _scope_plain(pane, "group")
            assert "group" not in (
                pane.query_one("#statistics-hints", Static).render().plain
            )
    
            pane._set_view("macros")
            await _wait_statistics_settled(page, pane)
            cached_calls = len(calls)
            pane.action_cycle_group()
            await page.pause()
            assert pane._macros_group_by == "model"
            assert len(calls) == cached_calls
            assert "Macros · By Model" in _scope_plain(pane, "group")
    
            pane._set_view("providers")
            await _wait_statistics_settled(page, pane)
            cached_calls = len(calls)
            pane.action_cycle_group()
            await page.pause()
            assert pane._projects_group_by == "repo"
            assert pane._macros_group_by == "model"
            assert pane._perf_group_by == "subsystem"
            assert len(calls) == cached_calls
            assert pane.query_one("#statistics-scope-group", Static).display is False
    
            pane._set_view("projects")
>           await _wait_statistics_settled(page, pane)

tests/ace/tui/test_statistics_pane_filters.py:192: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/_statistics_pane_ui_helpers.py:98: in wait_statistics_settled
    await page.wait_for(
src/sase/ace/testing/ace_page.py:577: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f7056e90a90>

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
E               AssertionError: wait_for() timed out after 30.0s — predicate never returned True

src/sase/ace/testing/wait.py:64: AssertionError
___ test_unresolvable_label_toasts_marks_it_dangling_and_does_not_renavigate ___
[gw17] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f4c9f44e900>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw17/test_unresolvable_label_toasts0')

    async def test_unresolvable_label_toasts_marks_it_dangling_and_does_not_renavigate(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        workspace = tmp_path / "ws"
        workspace.mkdir()
        loop_thread = threading.current_thread()
        git_calls: list[Path] = []
        resolve_threads: list[int | None] = []
    
        def fake_git(directory: Path) -> tuple[str, ...] | None:
            git_calls.append(directory)
            return ()
    
        def spy_resolve(
            ref: str, *, context: LinkResolutionContext | None = None
        ) -> LinkResolution:
            resolve_threads.append(threading.current_thread().ident)
            assert threading.current_thread() is not loop_thread
            return resolve_link(ref, context=context)
    
        monkeypatch.setattr("sase.pager._resolve_path_search._git_ls_files", fake_git)
        monkeypatch.setattr("sase.pager.screen.resolve_ref", spy_resolve)
        notifications: list[tuple[str, str]] = []
    
        def notify(message: str, *, severity: str = "information", **_kwargs: Any) -> None:
            notifications.append((message, severity))
    
        section = PagerSection(
            identity="file:/tmp/source.py",
            title="source.py",
            kind="file",
            body="see src/missing.py for details\n",
            link_anchors=(LinkAnchor(workspace),),
        )
        app = SasePager(
            PagerDocument(sections=(section,), title="source.py", origin=PagerOrigin.FILE)
        )
        monkeypatch.setattr(app, "notify", notify)
        async with app.run_test(size=(80, 24)) as pilot:
            screen = pager_screen(app)
            await pilot.pause()
            await pilot.press("0")
            await pilot.pause(0.1)
            await pilot.pause(0.1)
    
>           assert git_calls == [workspace.resolve()]
E           AssertionError: assert [] == [PosixPath('/..._toasts0/ws')]
E             
E             Right contains one more item: PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw17/test_unresolvable_label_toasts0/ws')
E             Use -v to get more diff

tests/pager/test_app_dangling.py:65: AssertionError
______________ test_three_update_cycles_refresh_bash_fish_and_zsh ______________
[gw20] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/test_three_update_cycles_refre0')
capsys = <_pytest.capture.CaptureFixture object at 0x7f8d13fabd10>

    def test_three_update_cycles_refresh_bash_fish_and_zsh(
        tmp_path: Path,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        scripts = install_unmanaged_shells(tmp_path)
        mark_scripts_stale(scripts)
        for stamp in (read_stamp(shell) for shell in scripts):
            assert stamp is not None
            assert stamp.version == OLD_STAMP_VERSION
    
        snapshots: list[dict[str, str]] = []
        for _ in range(SOAK_CYCLES):
            payload = successful_update(tmp_path, capsys)
>           assert_unmanaged_refresh(scripts, payload)

tests/completion/test_update_refresh_soak.py:63: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

scripts = {'bash': PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/test_three_update_cycles_refre0/complet...th('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/test_three_update_cycles_refre0/completions/zsh/_sase')}
payload = {'changed': True, 'command': ['uv', 'tool', 'upgrade', '--color', 'never', 'sase'], 'completion_refresh': {'attempted'...hree_update_cycles_refre0/completions/zsh/_sase'}]}, 'counts': {'already_current': 1, 'removed': 0, 'updated': 2}, ...}

    def assert_unmanaged_refresh(
        scripts: Mapping[str, Path],
        payload: Mapping[str, Any],
        *,
        exact: bool = True,
    ) -> None:
        """Assert a successful refresh rewrote stamps, scripts, and zsh bytecode."""
        wanted = tuple(scripts)
        by_shell = refresh_by_shell(payload)
        if exact:
            assert set(by_shell) == set(wanted)
        else:
            assert set(wanted) <= set(by_shell)
        for shell in wanted:
            outcome = by_shell[shell]
            script = scripts[shell]
            text = script.read_text(encoding="utf-8")
>           assert outcome["ok"] is True, outcome
                   ^^^^^^^^^^^^^^^^^^^^^
E           AssertionError: {'detail': 'zcompile timed out for /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/home-5fvdevc8/.sase/completion/grammar/1cd4bfe2cc6377809108cf83/zsh/.stage.1733152/._sase.1733152.tmp', 'ok': False, 'shell': 'zsh', 'target': '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw20/test_three_update_cycles_refre0/completions/zsh/_sase'}

tests/completion/_update_refresh_harness.py:125: AssertionError
_____________ test_provider_timer_thread_starts_before_live_enter ______________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_provider_timer_thread_starts_before_live_enter() -> None:
        """The named timer thread exists before Live takes stdout."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        seen_during_enter: list[threading.Thread] = []
        original_enter = Live.__enter__
    
        def tracking_enter(self: Live) -> Live:
            seen_during_enter.extend(_provider_timer_threads(existing_thread_ids))
            return original_enter(self)
    
        with (
            patch.object(Live, "__enter__", tracking_enter),
            patch("sase.output.time.sleep", return_value=None),
            provider_timer("Short operation"),
        ):
>           _wait_for_provider_timer_thread(existing_thread_ids)

tests/test_output.py:148: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {139921494890176, 139921511675584, 139921830438592, 139922072655552, 139922565363584}

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
✅ Short operation completed in 01:02
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui.command_line._completion_sources_shared
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.ace.tui._bench_tui_jk_helpers
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests.monitor._no_new_receipt
    self.import_plugin(import_spec)

.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_view_foundation.py::test_open_moves_detail_ownership_to_archive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/core/content_layout_wire.py:270: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    for item in cast(list[Any], raw.get("legacy", []))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_memory_pane_review.py::test_compute_memory_badge_returns_count_and_token
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/nodes.py:344: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    return (x[1] for x in self.iter_markers_with_node(name=name))
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object _recheck_grammar_key at 0x7f5b9c9e79a0>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/modals/test_glossary_preview_modal.py::test_glossary_modal_follows_references_and_goes_back
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/rich/text.py:144: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def __init__(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object _record_history_async.<locals>._record at 0x7f5b9cc86180>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/legacy_xprompt_syntax.py:94: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    result = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object CommandLineScreen._load_tail_worker at 0x7fdf6c185c40>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/test_agent_archive_proof.py::test_open_needs_no_flag_and_parks_the_inbox
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/core/content_layout_wire.py:368: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    formats=tuple(str(item) for item in raw.get("formats", [])),
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_display_group_fold_repaint.py::test_unchanged_fold_state_stays_on_patch_path
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_tabs_launch_view.py::test_apply_launch_view_tab_skips
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    payload = binding(
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_releases_attempt_continuation_pointers changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=1732675) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=1732227) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=1733361) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace[hostile ambient value] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=1732285) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/macro/workflow_runner.py:477: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=1732227) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=1733434) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
639.86s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
492.24s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
477.69s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
444.50s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
391.91s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
383.38s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
358.05s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
354.61s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
330.56s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
317.16s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
310.87s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
289.14s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
268.38s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
189.55s setup    tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
175.83s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
173.38s setup    tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
167.75s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
162.84s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
162.53s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
152.96s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
=========================== short test summary info ============================
FAILED tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
FAILED tests/pager/test_app_dangling.py::test_unresolvable_label_toasts_marks_it_dangling_and_does_not_renavigate
FAILED tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
FAILED tests/test_output.py::test_provider_timer_thread_starts_before_live_enter
==== 4 failed, 60609 passed, 17 skipped, 112 warnings in 4711.44s (1:18:31) ====
[contention-diag] +4720s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 425 | 1 parent rss 0.0G pss 0.0G | host avail 38.0G/62.7G swapfree 47.7G/64.0G oom_kill +0 | psi10 mem 2.12/0.01 io 0.06 cpu 6.34 | cgroup 2.5G/max oom_kill 0 | free scratch 294.6G/44793470i tmp 26.1G/985882i workspace 294.6G/44793470i | repeat-01 collected 26/26 workers (60629 items) tests 60629 done 4 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4720s, 303 samples, 0 signal(s); peaks: cgroup_current 16.4G, min_free_scratch 290.4G, min_free_tmp 26.1G, min_free_workspace 290.4G, min_inodes_scratch 44624537, min_inodes_tmp 985581, min_inodes_workspace 44624537, min_mem_available 13.7G, min_swap_free 39.0G, oom_kill_delta 0, pressure_memory_full 22.52, pswpin_delta 2999512, pswpout_delta 4904243, scratch_bytes 0.7G, soak_procs 44, soak_pss 14.1G, soak_rss 16.1G, soak_swap 3.7G, soak_threads 259

contention tally: 4 node(s) failed across 1 repeat(s) in 4719.8s; red repeats: 1
  1/1  tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result  (repeats 1)
  1/1  tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh  (repeats 1)
  1/1  tests/pager/test_app_dangling.py::test_unresolvable_label_toasts_marks_it_dangling_and_does_not_renavigate  (repeats 1)
  1/1  tests/test_output.py::test_provider_timer_thread_starts_before_live_enter  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics
error: recipe `test-contention` failed on line 779 with exit code 1
RESOURCE child_user_seconds=8724.67 child_system_seconds=648.75 max_child_rss_kib=1143436
ELAPSED_SECONDS=4721.95
TEST_EXIT_CODE=1

