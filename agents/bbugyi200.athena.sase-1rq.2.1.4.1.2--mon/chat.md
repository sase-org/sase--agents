# Chat History - ace-run (sase-1rq.2.1.4.1.2--mon)

- **TIMESTAMP:** 2026-11-07 16:37:10 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1rq.2.1.4.1.2--mon

## Prompt

sase monitor start --command 'systemd-run --user --scope -q -p MemoryMax=15G -p MemorySwapMax=4G -- env SASE_CONTENTION_REPEAT=1 just test-contention' --reason 'Full unchanged-shape local contention repeat (full default selection, 26 workers, taskset cpus 0,1, SASE_CONTENTION_REPEAT=1) on the sharded-collection fix, under the same 15G RAM + 4G swap cap as evidence monitor kyhnsmgpcjx9, to prove the soak now survives collection and reaches its tally (survival phase sase-1rq.2.1.4.1.2)'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.44.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-contention          │
└───────────────────────────────────────────────────────┘

---------- Running default-lane pytest contention harness... ----------
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5669 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 4100036, sampler pid 4100249 on cpus 0-63 (soak cpus 0-1), python 3.14.7, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/run-p4099647-i12485445.scope max 16106127360, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 32.2G/62.7G swapfree 48.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.08 cpu 0.0 | cgroup 0.1G/16106127360 oom_kill 0 | free scratch 331.3G/45415936i tmp 30.3G/1036886i workspace 331.3G/45415936i | scratch used 0.0G in 13 entries | progress none yet
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +15s soak 28p/80t rss 2.4G pss 2.1G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.3G pss 2.0G | host avail 28.6G/62.7G swapfree 49.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.14 cpu 7.06 | cgroup 2.1G/16106127360 oom_kill 0 | free scratch 331.3G/45414989i tmp 30.3G/1036886i workspace 331.3G/45414989i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +30s soak 28p/80t rss 4.2G pss 3.7G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.1G pss 3.6G | host avail 26.2G/62.7G swapfree 49.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.02 cpu 9.6 | cgroup 3.8G/16106127360 oom_kill 0 | free scratch 331.3G/45414237i tmp 30.3G/1036886i workspace 331.3G/45414237i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +45s soak 28p/83t rss 5.6G pss 5.1G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.5G pss 5.0G | host avail 26.4G/62.7G swapfree 49.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.05 cpu 10.74 | cgroup 5.2G/16106127360 oom_kill 0 | free scratch 331.2G/45411794i tmp 30.3G/1036885i workspace 331.2G/45411794i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +61s soak 28p/88t rss 6.7G pss 6.1G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.5G pss 6.0G | host avail 24.4G/62.7G swapfree 49.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.73 cpu 10.91 | cgroup 6.3G/16106127360 oom_kill 0 | free scratch 331.2G/45411220i tmp 30.3G/1036886i workspace 331.2G/45411220i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +76s soak 28p/89t rss 7.7G pss 7.1G swap 0.0G majflt 3 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.6G pss 7.0G | host avail 23.2G/62.7G swapfree 49.6G/64.0G oom_kill +0 | psi10 mem 0.36/0.36 io 0.96 cpu 11.45 | cgroup 7.5G/16106127360 oom_kill 0 | free scratch 331.2G/45410693i tmp 30.3G/1036886i workspace 331.2G/45410693i | repeat-01 collected 18/26 workers (41981 items) tests 0 done 0 failed
contention shards: 26 workers collected 60588 items in total (2057-2543 per worker)
26 workers [2334 items]

........................................................................ [  2%]
........................................................................ [  5%]
........................................................................ [  8%]
........................................................................ [ 11%]
........................................................................ [ 14%]
........................................................................ [ 17%]
........................................................................ [ 20%]
........................................................................ [ 23%]
........................................................................ [ 26%]
........................................................................ [ 29%]
.................[contention-diag] +91s soak 31p/119t rss 8.3G pss 7.6G swap 0.0G majflt 15 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.1G pss 7.4G, 3 descendant rss 0.0G pss 0.0G | host avail 21.0G/62.7G swapfree 49.6G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 1.32 cpu 10.24 | cgroup 8.0G/16106127360 oom_kill 0 | free scratch 331.2G/45407463i tmp 30.3G/1036886i workspace 331.2G/45407463i | repeat-01 collected 26/26 workers (60588 items) tests 735 done 0 failed | 26 in flight, oldest 4s gw3 tests/ace/tui/actions/test_prompt_memory_panel_open.py::test_gm_opens_panel_and_escape_restores_normal_focus
....................................................... [ 32%]
........................................................................ [ 35%]
........................................................................ [ 38%]
........................................................................ [ 41%]
........................................................................ [ 44%]
..............................................................[contention-diag] +106s soak 29p/146t rss 8.7G pss 7.9G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.7G, 1 descendant rss 0.1G pss 0.1G | host avail 20.5G/62.7G swapfree 49.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.4 cpu 9.98 | cgroup 8.3G/16106127360 oom_kill 0 | free scratch 331.2G/45405834i tmp 30.3G/1036886i workspace 331.2G/45405834i | repeat-01 collected 26/26 workers (60588 items) tests 1128 done 0 failed | 26 in flight, oldest 20s gw3 tests/ace/tui/actions/test_prompt_memory_panel_open.py::test_gm_opens_panel_and_escape_restores_normal_focus
.......... [ 47%]
........................................................................ [ 50%]
........................................................................ [ 53%]
............[contention-diag] +122s soak 30p/159t rss 9.0G pss 8.2G swap 0.0G majflt 22 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 7.9G, 2 descendant rss 0.1G pss 0.1G | host avail 19.3G/62.7G swapfree 49.6G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 1.87 cpu 9.47 | cgroup 8.4G/16106127360 oom_kill 0 | free scratch 330.7G/45378923i tmp 30.3G/1036886i workspace 330.7G/45378923i | scratch used 0.0G in 3644 entries | repeat-01 collected 26/26 workers (60588 items) tests 1286 done 0 failed | 26 in flight, oldest 33s gw13 tests/ace/tui/command_line/test_completion_sources_cd.py::test_cd_completes_directories_projects_and_unpin_on_the_screen
............................................................ [ 56%]
........................................................................ [ 59%]
...............................................................F........ [ 62%]
..........................................[contention-diag] +138s soak 31p/158t rss 9.2G pss 8.4G swap 0.0G majflt 13 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.2G, 3 descendant rss 0.1G pss 0.1G | host avail 21.2G/62.7G swapfree 49.6G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.0 cpu 10.75 | cgroup 8.7G/16106127360 oom_kill 0 | free scratch 330.5G/45376900i tmp 30.3G/1036886i workspace 330.5G/45376900i | repeat-01 collected 26/26 workers (60588 items) tests 1543 done 1 failed | 25 in flight, oldest 48s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
.............................. [ 65%]
........................................................................ [ 68%]
........................................................................ [ 71%]
..............................................................[contention-diag] +153s soak 30p/177t rss 9.4G pss 8.6G swap 0.0G majflt 55 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.3G, 2 descendant rss 0.1G pss 0.1G | host avail 20.3G/62.7G swapfree 49.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.65 cpu 10.41 | cgroup 8.8G/16106127360 oom_kill 0 | free scratch 330.6G/45375468i tmp 30.3G/1036886i workspace 330.6G/45375468i | repeat-01 collected 26/26 workers (60588 items) tests 1779 done 1 failed | 26 in flight, oldest 63s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
.......... [ 74%]
........................................................................ [ 77%]
.................................................[contention-diag] +168s soak 32p/186t rss 9.6G pss 8.7G swap 0.0G majflt 13 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.5G, 4 descendant rss 0.1G pss 0.1G | host avail 20.5G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.68 cpu 10.8 | cgroup 8.8G/16106127360 oom_kill 0 | free scratch 330.7G/45387454i tmp 30.3G/1036882i workspace 330.7G/45387454i | repeat-01 collected 26/26 workers (60588 items) tests 1917 done 1 failed | 26 in flight, oldest 70s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................... [ 80%]
........................................................................ [ 83%]
........................................................................ [ 86%]
.....................................................[contention-diag] +183s soak 31p/180t rss 9.7G pss 8.8G swap 0.0G majflt 14 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.6G, 3 descendant rss 0.1G pss 0.0G | host avail 20.3G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.27 cpu 10.71 | cgroup 9.0G/16106127360 oom_kill 0 | free scratch 330.7G/45386058i tmp 30.3G/1036884i workspace 330.7G/45386058i | repeat-01 collected 26/26 workers (60588 items) tests 2132 done 1 failed | 25 in flight, oldest 85s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................... [ 89%]
........................................................................ [ 92%]
........................................................................ [ 95%]
........................................................[contention-diag] +199s soak 29p/185t rss 9.8G pss 8.9G swap 0.0G majflt 18 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.7G, 1 descendant rss 0.1G pss 0.1G | host avail 20.1G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.33 cpu 10.26 | cgroup 9.1G/16106127360 oom_kill 0 | free scratch 330.7G/45384443i tmp 30.3G/1036886i workspace 330.7G/45384443i | repeat-01 collected 26/26 workers (60588 items) tests 2344 done 1 failed | 26 in flight, oldest 100s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................ [ 98%]
........................................................................ [101%]
........................................................................ [104%]
........................................................................ [107%]
........................................................[contention-diag] +214s soak 29p/190t rss 10.0G pss 9.1G swap 0.0G majflt 21 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 8.8G, 1 descendant rss 0.1G pss 0.1G | host avail 19.0G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 1.15 cpu 10.87 | cgroup 9.3G/16106127360 oom_kill 0 | free scratch 330.7G/45382849i tmp 30.3G/1036886i workspace 330.7G/45382849i | repeat-01 collected 26/26 workers (60588 items) tests 2622 done 1 failed | 26 in flight, oldest 115s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................ [110%]
........................................................................ [113%]
........................................................................ [116%]
........................................................................ [119%]
........................................................................ [122%]
.........................................................[contention-diag] +229s soak 30p/200t rss 10.1G pss 9.2G swap 0.0G majflt 21 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.0G, 2 descendant rss 0.1G pss 0.1G | host avail 19.8G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.25 cpu 11.86 | cgroup 9.4G/16106127360 oom_kill 0 | free scratch 330.7G/45381176i tmp 30.3G/1036886i workspace 330.7G/45381176i | repeat-01 collected 26/26 workers (60588 items) tests 3008 done 1 failed | 26 in flight, oldest 131s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............... [125%]
..................................................[contention-diag] +244s soak 30p/203t rss 10.3G pss 9.4G swap 0.0G majflt 25 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.0G, 2 descendant rss 0.2G pss 0.2G | host avail 19.6G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.26 cpu 11.23 | cgroup 9.6G/16106127360 oom_kill 0 | free scratch 330.7G/45379991i tmp 30.3G/1036886i workspace 330.7G/45379991i | scratch used 0.1G in 8268 entries | repeat-01 collected 26/26 workers (60588 items) tests 3070 done 1 failed | 26 in flight, oldest 146s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................... [128%]
........................................................................ [131%]
........................................................................ [134%]
.....................................................[contention-diag] +260s soak 37p/208t rss 10.6G pss 9.6G swap 0.0G majflt 31 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.1G, 9 descendant rss 0.4G pss 0.3G | host avail 20.0G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.53 cpu 11.22 | cgroup 9.8G/16106127360 oom_kill 0 | free scratch 330.7G/45378680i tmp 30.3G/1036886i workspace 330.7G/45378680i | repeat-01 collected 26/26 workers (60588 items) tests 3283 done 1 failed | 26 in flight, oldest 162s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................... [137%]
........................................................................ [140%]
...[contention-diag] +275s soak 34p/199t rss 10.4G pss 9.5G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.2G, 6 descendant rss 0.1G pss 0.1G | host avail 18.5G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.03 cpu 11.88 | cgroup 9.7G/16106127360 oom_kill 0 | free scratch 330.6G/45377430i tmp 30.3G/1036885i workspace 330.6G/45377430i | repeat-01 collected 26/26 workers (60588 items) tests 3387 done 1 failed | 26 in flight, oldest 177s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.............................................[contention-diag] +291s soak 35p/222t rss 10.7G pss 9.7G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.3G, 7 descendant rss 0.3G pss 0.2G | host avail 17.9G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.0 cpu 11.5 | cgroup 9.9G/16106127360 oom_kill 0 | free scratch 330.6G/45376185i tmp 30.3G/1036886i workspace 330.6G/45376185i | repeat-01 collected 26/26 workers (60588 items) tests 3431 done 1 failed | 26 in flight, oldest 192s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..............[contention-diag] +306s soak 36p/232t rss 10.8G pss 9.8G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.4G, 8 descendant rss 0.3G pss 0.2G | host avail 19.2G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.18 cpu 11.53 | cgroup 10.0G/16106127360 oom_kill 0 | free scratch 330.6G/45374933i tmp 30.3G/1036886i workspace 330.6G/45374932i | repeat-01 collected 26/26 workers (60588 items) tests 3446 done 1 failed | 26 in flight, oldest 208s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......... [143%]
.......F................................................................ [146%]
.................[contention-diag] +322s soak 36p/218t rss 10.7G pss 9.7G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.4G, 8 descendant rss 0.2G pss 0.1G | host avail 17.9G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.43 cpu 11.36 | cgroup 10.0G/16106127360 oom_kill 0 | free scratch 330.6G/45373579i tmp 30.3G/1036886i workspace 330.6G/45373578i | repeat-01 collected 26/26 workers (60588 items) tests 3541 done 2 failed | 26 in flight, oldest 223s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................................... [149%]
........................................................................ [152%]
........................................................................ [155%]
.........[contention-diag] +337s soak 33p/210t rss 10.7G pss 9.7G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.5G, 5 descendant rss 0.1G pss 0.0G | host avail 18.3G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 11.3 | cgroup 9.9G/16106127360 oom_kill 0 | free scratch 330.6G/45372382i tmp 30.3G/1036884i workspace 330.6G/45372382i | repeat-01 collected 26/26 workers (60588 items) tests 3753 done 2 failed | 26 in flight, oldest 238s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................................... [158%]
.............................[contention-diag] +352s soak 36p/217t rss 10.9G pss 9.9G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.6G, 8 descendant rss 0.2G pss 0.1G | host avail 19.3G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.65 cpu 11.95 | cgroup 10.1G/16106127360 oom_kill 0 | free scratch 330.6G/45371289i tmp 30.3G/1036885i workspace 330.6G/45371289i | repeat-01 collected 26/26 workers (60588 items) tests 3843 done 2 failed | 26 in flight, oldest 254s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................... [161%]
........................................................................ [164%]
.................[contention-diag] +368s soak 32p/200t rss 10.9G pss 9.8G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.6G, 4 descendant rss 0.1G pss 0.0G | host avail 19.7G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.32 cpu 11.16 | cgroup 10.1G/16106127360 oom_kill 0 | free scratch 330.8G/45382779i tmp 30.3G/1035774i workspace 330.8G/45382779i | scratch used 0.1G in 11141 entries | repeat-01 collected 26/26 workers (60588 items) tests 3962 done 2 failed | 25 in flight, oldest 269s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................[contention-diag] +383s soak 34p/206t rss 10.9G pss 9.9G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.7G, 6 descendant rss 0.1G pss 0.1G | host avail 18.4G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.61 cpu 12.09 | cgroup 10.2G/16106127360 oom_kill 0 | free scratch 330.8G/45382182i tmp 30.3G/1035774i workspace 330.8G/45382182i | repeat-01 collected 26/26 workers (60588 items) tests 4025 done 2 failed | 26 in flight, oldest 284s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.... [167%]
...............................................................[contention-diag] +398s soak 34p/208t rss 11.0G pss 10.0G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 6 descendant rss 0.1G pss 0.1G | host avail 20.0G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.89 cpu 12.06 | cgroup 10.3G/16106127360 oom_kill 0 | free scratch 330.8G/45381095i tmp 30.3G/1035774i workspace 330.8G/45381095i | repeat-01 collected 26/26 workers (60588 items) tests 4094 done 2 failed | 26 in flight, oldest 300s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......... [170%]
........................................................................ [173%]
.........[contention-diag] +413s soak 36p/215t rss 11.3G pss 10.2G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 9.8G, 8 descendant rss 0.3G pss 0.3G | host avail 19.9G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.88 cpu 12.5 | cgroup 10.5G/16106127360 oom_kill 0 | free scratch 330.8G/45380185i tmp 30.3G/1035774i workspace 330.8G/45380185i | repeat-01 collected 26/26 workers (60588 items) tests 4182 done 2 failed | 26 in flight, oldest 315s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..........................[contention-diag] +429s soak 35p/207t rss 11.3G pss 10.2G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G, 7 descendant rss 0.3G pss 0.2G | host avail 19.2G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.66 cpu 11.81 | cgroup 10.5G/16106127360 oom_kill 0 | free scratch 330.8G/45379443i tmp 30.3G/1035773i workspace 330.8G/45379443i | repeat-01 collected 26/26 workers (60588 items) tests 4207 done 2 failed | 26 in flight, oldest 330s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..............[contention-diag] +444s soak 34p/215t rss 11.1G pss 10.1G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.9G, 6 descendant rss 0.1G pss 0.1G | host avail 18.5G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.43 cpu 10.88 | cgroup 10.4G/16106127360 oom_kill 0 | free scratch 330.8G/45378543i tmp 30.3G/1035772i workspace 330.8G/45378543i | repeat-01 collected 26/26 workers (60588 items) tests 4224 done 2 failed | 26 in flight, oldest 346s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................... [176%]
...................[contention-diag] +459s soak 34p/222t rss 11.2G pss 10.2G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 9.9G, 6 descendant rss 0.1G pss 0.1G | host avail 19.0G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 1.29 cpu 11.54 | cgroup 10.4G/16106127360 oom_kill 0 | free scratch 330.8G/45377762i tmp 30.3G/1035771i workspace 330.8G/45377762i | repeat-01 collected 26/26 workers (60588 items) tests 4262 done 2 failed | 26 in flight, oldest 361s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................................................... [179%]
....................................................[contention-diag] +475s soak 36p/219t rss 11.3G pss 10.3G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 10.0G, 8 descendant rss 0.2G pss 0.1G | host avail 21.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.22 cpu 12.35 | cgroup 10.5G/16106127360 oom_kill 0 | free scratch 330.8G/45376951i tmp 30.3G/1035770i workspace 330.8G/45376951i | repeat-01 collected 26/26 workers (60588 items) tests 4365 done 2 failed | 26 in flight, oldest 376s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................... [182%]
........................................................................ [185%]
......................................................[contention-diag] +490s soak 39p/218t rss 11.3G pss 10.2G swap 0.0G majflt 28 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.0G, 11 descendant rss 0.2G pss 0.1G | host avail 19.6G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.74 cpu 11.77 | cgroup 10.5G/16106127360 oom_kill 0 | free scratch 330.8G/45376025i tmp 30.3G/1035767i workspace 330.8G/45376025i | scratch used 0.1G in 13269 entries | repeat-01 collected 26/26 workers (60588 items) tests 4516 done 2 failed | 26 in flight, oldest 391s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................. [188%]
...[contention-diag] +506s soak 38p/225t rss 11.3G pss 10.2G swap 0.0G majflt 29 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.0G, 10 descendant rss 0.1G pss 0.0G | host avail 20.7G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.64 cpu 12.41 | cgroup 10.5G/16106127360 oom_kill 0 | free scratch 330.8G/45375139i tmp 30.3G/1035767i workspace 330.8G/45375139i | repeat-01 collected 26/26 workers (60588 items) tests 4539 done 2 failed | 26 in flight, oldest 82s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
..............................[contention-diag] +521s soak 39p/231t rss 11.4G pss 10.3G swap 0.0G majflt 29 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.1G, 11 descendant rss 0.2G pss 0.1G | host avail 20.5G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.54 cpu 12.27 | cgroup 10.6G/16106127360 oom_kill 0 | free scratch 330.8G/45374038i tmp 30.3G/1035755i workspace 330.8G/45374038i | repeat-01 collected 26/26 workers (60588 items) tests 4567 done 2 failed | 26 in flight, oldest 97s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
....................................... [191%]
........................................................................ [194%]
...............................[contention-diag] +536s soak 35p/228t rss 11.4G pss 10.4G swap 0.0G majflt 29 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.1G pss 10.1G, 7 descendant rss 0.1G pss 0.1G | host avail 21.5G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.44 cpu 12.11 | cgroup 10.7G/16106127360 oom_kill 0 | free scratch 330.7G/45372932i tmp 30.3G/1035752i workspace 330.7G/45372932i | repeat-01 collected 26/26 workers (60588 items) tests 4702 done 2 failed | 26 in flight, oldest 113s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_explicit_empty_filter_commit_restores_unfiltered_view
........................................F [197%]
.......[contention-diag] +552s soak 35p/214t rss 11.4G pss 10.4G swap 0.0G majflt 29 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.1G pss 10.2G, 7 descendant rss 0.1G pss 0.1G | host avail 20.8G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.86 cpu 11.8 | cgroup 10.7G/16106127360 oom_kill 0 | free scratch 330.7G/45372021i tmp 30.3G/1035752i workspace 330.7G/45372021i | repeat-01 collected 26/26 workers (60588 items) tests 4757 done 3 failed | 26 in flight, oldest 94s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
............................................[contention-diag] +567s soak 34p/218t rss 11.4G pss 10.4G swap 0.0G majflt 29 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.2G, 6 descendant rss 0.1G pss 0.0G | host avail 20.7G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.21 cpu 11.26 | cgroup 10.7G/16106127360 oom_kill 0 | free scratch 330.5G/45360772i tmp 30.3G/1035752i workspace 330.5G/45360772i | repeat-01 collected 26/26 workers (60588 items) tests 4803 done 3 failed | 26 in flight, oldest 94s gw22 tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_fresh_app_instance_hides_removed_rows
..............F[contention-diag] +582s soak 29p/235t rss 11.5G pss 10.5G swap 0.0G majflt 29 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.2G, 1 descendant rss 0.1G pss 0.1G | host avail 19.3G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.76 cpu 10.62 | cgroup 10.8G/16106127360 oom_kill 0 | free scratch 330.5G/45360114i tmp 30.3G/1035752i workspace 330.5G/45360114i | repeat-01 collected 26/26 workers (60588 items) tests 4818 done 4 failed | 26 in flight, oldest 55s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
...... [200%]
.................[contention-diag] +598s soak 28p/233t rss 11.4G pss 10.5G swap 0.0G majflt 29 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.3G | host avail 18.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.94 cpu 10.89 | cgroup 10.8G/16106127360 oom_kill 0 | free scratch 330.5G/45359404i tmp 30.3G/1035752i workspace 330.5G/45359404i | repeat-01 collected 26/26 workers (60588 items) tests 4840 done 4 failed | 26 in flight, oldest 70s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
....................................................... [203%]
......[contention-diag] +613s soak 32p/237t rss 11.6G pss 10.5G swap 0.0G majflt 29 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.3G, 4 descendant rss 0.1G pss 0.1G | host avail 20.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.84 cpu 12.26 | cgroup 10.9G/16106127360 oom_kill 0 | free scratch 330.5G/45358437i tmp 30.3G/1035752i workspace 330.5G/45358437i | scratch used 0.1G in 15107 entries | repeat-01 collected 26/26 workers (60588 items) tests 4900 done 4 failed | 26 in flight, oldest 86s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
.....................................................[contention-diag] +628s soak 30p/221t rss 11.6G pss 10.6G swap 0.0G majflt 32 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.4G, 2 descendant rss 0.1G pss 0.1G | host avail 19.9G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.57 cpu 13.71 | cgroup 10.9G/16106127360 oom_kill 0 | free scratch 330.5G/45357621i tmp 30.3G/1035752i workspace 330.5G/45357621i | repeat-01 collected 26/26 workers (60588 items) tests 4952 done 4 failed | 26 in flight, oldest 64s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
............. [206%]
.........[contention-diag] +644s soak 29p/226t rss 11.6G pss 10.6G swap 0.0G majflt 131 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 19.5G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 12.82 | cgroup 10.9G/16106127360 oom_kill 0 | free scratch 330.5G/45356790i tmp 30.3G/1035749i workspace 330.5G/45356790i | repeat-01 collected 26/26 workers (60588 items) tests 4976 done 4 failed | 26 in flight, oldest 67s gw22 tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
..........................................[contention-diag] +659s soak 28p/231t rss 11.6G pss 10.6G swap 0.0G majflt 43 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 10.4G | host avail 19.0G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.88 cpu 12.59 | cgroup 11.0G/16106127360 oom_kill 0 | free scratch 330.5G/45355834i tmp 30.3G/1035749i workspace 330.5G/45355834i | repeat-01 collected 26/26 workers (60588 items) tests 5018 done 4 failed | 26 in flight, oldest 70s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
.................[contention-diag] +674s soak 30p/221t rss 11.8G pss 10.7G swap 0.0G majflt 43 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 10.5G, 2 descendant rss 0.1G pss 0.1G | host avail 19.9G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.44 cpu 12.6 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 330.4G/45355049i tmp 30.3G/1035749i workspace 330.4G/45355049i | repeat-01 collected 26/26 workers (60588 items) tests 5034 done 4 failed | 26 in flight, oldest 55s gw18 tests/ace/tui/command_line/test_policy_io.py::test_poll_once_keeps_settled_elapsed_after_await
.... [209%]
............................[contention-diag] +690s soak 28p/220t rss 11.7G pss 10.7G swap 0.0G majflt 43 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.5G pss 10.5G | host avail 19.3G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.66 cpu 13.83 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 330.6G/45385351i tmp 30.3G/1035748i workspace 330.6G/45385351i | repeat-01 collected 26/26 workers (60588 items) tests 5066 done 4 failed | 26 in flight, oldest 65s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_invalid_query_shows_inline_error_and_keeps_last_good_list
............................................ [212%]
......[contention-diag] +705s soak 28p/225t rss 11.7G pss 10.7G swap 0.0G majflt 43 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.5G pss 10.5G | host avail 18.1G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 2.32 cpu 12.86 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 331.1G/45479816i tmp 30.3G/1035748i workspace 331.1G/45479817i | repeat-01 collected 26/26 workers (60588 items) tests 5117 done 4 failed | 26 in flight, oldest 55s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
........................................................[contention-diag] +721s soak 29p/217t rss 11.8G pss 10.8G swap 0.0G majflt 43 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.5G pss 10.5G, 1 descendant rss 0.1G pss 0.1G | host avail 18.3G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.07 cpu 12.69 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 331.3G/45516893i tmp 30.3G/1035748i workspace 331.3G/45516893i | repeat-01 collected 26/26 workers (60588 items) tests 5167 done 4 failed | 26 in flight, oldest 63s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_picker_acts_on_focused_split_panel
.......... [215%]
.......................................[contention-diag] +736s soak 30p/217t rss 11.9G pss 10.8G swap 0.0G majflt 43 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.6G, 2 descendant rss 0.1G pss 0.1G | host avail 18.3G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.83 cpu 12.5 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 331.2G/45516005i tmp 30.3G/1035748i workspace 331.2G/45516005i | scratch used 0.1G in 16905 entries | repeat-01 collected 26/26 workers (60588 items) tests 5219 done 4 failed | 26 in flight, oldest 57s gw18 tests/ace/tui/command_line/test_policy_io.py::test_scrolled_out_running_block_is_not_tailed
................................. [218%]
......[contention-diag] +751s soak 29p/225t rss 11.8G pss 10.8G swap 0.0G majflt 43 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 17.5G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.77 cpu 10.96 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 331.2G/45515025i tmp 30.3G/1035748i workspace 331.2G/45515025i | repeat-01 collected 26/26 workers (60588 items) tests 5261 done 4 failed | 26 in flight, oldest 54s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
.................................................................. [221%]
...[contention-diag] +767s soak 29p/229t rss 11.8G pss 10.8G swap 0.0G majflt 43 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.6G, 1 descendant rss 0.1G pss 0.1G | host avail 17.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 0.57 cpu 11.5 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 331.2G/45514325i tmp 30.3G/1035747i workspace 331.2G/45514325i | repeat-01 collected 26/26 workers (60588 items) tests 5330 done 4 failed | 26 in flight, oldest 56s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
..................................F.................................. [224%]
............................[contention-diag] +782s soak 28p/214t rss 11.8G pss 10.8G swap 0.0G majflt 43 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.6G | host avail 18.5G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 2.97/0.02 io 1.2 cpu 13.38 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 331.2G/45513505i tmp 30.3G/1035746i workspace 331.2G/45513505i | repeat-01 collected 26/26 workers (60588 items) tests 5417 done 5 failed | 25 in flight, oldest 71s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
............................................ [227%]
..........................................[contention-diag] +797s soak 29p/218t rss 11.8G pss 10.8G swap 0.0G majflt 44 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.7G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 17.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.73/0.0 io 1.51 cpu 12.72 | cgroup 11.1G/16106127360 oom_kill 0 | free scratch 331.2G/45512720i tmp 30.3G/1035745i workspace 331.2G/45512720i | repeat-01 collected 26/26 workers (60588 items) tests 5514 done 5 failed | 26 in flight, oldest 87s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_cancel_keys_dismiss_with_none
.............................. [230%]
........................................................................ [233%]
....................................................................[contention-diag] +813s soak 29p/213t rss 11.9G pss 10.9G swap 0.0G majflt 45 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.7G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 18.3G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.14/0.0 io 1.27 cpu 11.7 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 331.2G/45511615i tmp 30.3G/1035745i workspace 331.2G/45511615i | repeat-01 collected 26/26 workers (60588 items) tests 5669 done 5 failed | 26 in flight, oldest 51s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.... [236%]
........................................................................ [239%]
........................................................................ [242%]
........................................................................ [245%]
...[contention-diag] +828s soak 28p/214t rss 11.9G pss 10.9G swap 0.1G majflt 46 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.7G pss 10.7G | host avail 17.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 1.7 cpu 11.81 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 331.2G/45510426i tmp 30.3G/1035745i workspace 331.2G/45510426i | repeat-01 collected 26/26 workers (60588 items) tests 5907 done 5 failed | 26 in flight, oldest 66s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
...........................................[contention-diag] +843s soak 29p/227t rss 11.9G pss 10.9G swap 0.1G majflt 53 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.8G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 20.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.5 cpu 11.12 | cgroup 11.2G/16106127360 oom_kill 0 | free scratch 331.2G/45509373i tmp 30.3G/1035745i workspace 331.2G/45509373i | repeat-01 collected 26/26 workers (60588 items) tests 5947 done 5 failed | 26 in flight, oldest 82s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.......................... [248%]
...[contention-diag] +859s soak 31p/242t rss 12.1G pss 11.0G swap 0.1G majflt 87 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.8G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 19.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.55 cpu 11.82 | cgroup 11.3G/16106127360 oom_kill 0 | free scratch 331.2G/45508598i tmp 30.3G/1035745i workspace 331.2G/45508598i | scratch used 0.1G in 19533 entries | repeat-01 collected 26/26 workers (60588 items) tests 5975 done 5 failed | 26 in flight, oldest 97s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
........................[contention-diag] +875s soak 32p/250t rss 12.2G pss 11.0G swap 0.1G majflt 93 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.9G pss 10.8G, 4 descendant rss 0.1G pss 0.1G | host avail 18.8G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.6 cpu 11.12 | cgroup 11.4G/16106127360 oom_kill 0 | free scratch 331.2G/45506709i tmp 30.3G/1035745i workspace 331.2G/45506709i | repeat-01 collected 26/26 workers (60588 items) tests 5999 done 5 failed | 26 in flight, oldest 113s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............................................. [251%]
......................................................................[contention-diag] +890s soak 29p/221t rss 12.1G pss 11.0G swap 0.1G majflt 94 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 19.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.9 cpu 12.06 | cgroup 11.5G/16106127360 oom_kill 0 | free scratch 331.2G/45503397i tmp 30.3G/1035746i workspace 331.2G/45503397i | repeat-01 collected 26/26 workers (60588 items) tests 6117 done 5 failed | 26 in flight, oldest 128s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
.. [254%]
........................................................................ [257%]
.......................[contention-diag] +905s soak 29p/217t rss 12.1G pss 11.0G swap 0.1G majflt 110 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.9G pss 10.9G, 1 descendant rss 0.0G pss 0.0G | host avail 20.0G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.75 cpu 12.49 | cgroup 11.5G/16106127360 oom_kill 0 | free scratch 331.1G/45500822i tmp 30.3G/1035746i workspace 331.1G/45500822i | repeat-01 collected 26/26 workers (60588 items) tests 6212 done 5 failed | 26 in flight, oldest 144s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............................[contention-diag] +921s soak 31p/223t rss 12.1G pss 11.0G swap 0.1G majflt 113 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.9G pss 10.9G, 3 descendant rss 0.0G pss 0.0G | host avail 19.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.32/0.32 io 3.43 cpu 11.86 | cgroup 11.4G/16106127360 oom_kill 0 | free scratch 331.1G/45497785i tmp 30.3G/1035746i workspace 331.1G/45497785i | repeat-01 collected 26/26 workers (60588 items) tests 6243 done 5 failed | 26 in flight, oldest 73s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
..................... [260%]
........................................................................ [263%]
........................................................................ [266%]
...................................[contention-diag] +936s soak 29p/195t rss 12.2G pss 11.1G swap 0.1G majflt 118 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.0G pss 10.9G, 1 descendant rss 0.1G pss 0.1G | host avail 18.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 2.31 cpu 11.31 | cgroup 11.5G/16106127360 oom_kill 0 | free scratch 331.1G/45495103i tmp 30.3G/1035746i workspace 331.1G/45495103i | repeat-01 collected 26/26 workers (60588 items) tests 6418 done 5 failed | 26 in flight, oldest 60s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
..................................... [269%]
........................................................................ [272%]
.........................................[contention-diag] +951s soak 29p/202t rss 12.2G pss 11.1G swap 0.1G majflt 124 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.0G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 19.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.65 cpu 12.31 | cgroup 11.5G/16106127360 oom_kill 0 | free scratch 331.1G/45493919i tmp 30.3G/1035746i workspace 331.1G/45493919i | repeat-01 collected 26/26 workers (60588 items) tests 6581 done 5 failed | 26 in flight, oldest 47s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
............................... [275%]
..................[contention-diag] +967s soak 30p/219t rss 12.2G pss 11.2G swap 0.1G majflt 125 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.0G pss 11.0G, 2 descendant rss 0.1G pss 0.1G | host avail 19.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.76 cpu 12.73 | cgroup 11.5G/16106127360 oom_kill 0 | free scratch 331.1G/45492936i tmp 30.3G/1035746i workspace 331.1G/45492936i | repeat-01 collected 26/26 workers (60588 items) tests 6642 done 5 failed | 26 in flight, oldest 62s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
.......[contention-diag] +982s soak 29p/225t rss 12.2G pss 11.2G swap 0.1G majflt 125 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.0G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 18.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.36 cpu 12.0 | cgroup 11.5G/16106127360 oom_kill 0 | free scratch 331.1G/45492223i tmp 30.3G/1035746i workspace 331.1G/45492223i | scratch used 0.1G in 22044 entries | repeat-01 collected 26/26 workers (60588 items) tests 6649 done 5 failed | 26 in flight, oldest 77s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
...............................[contention-diag] +998s soak 29p/204t rss 12.2G pss 11.2G swap 0.1G majflt 125 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.0G pss 11.0G, 1 descendant rss 0.0G pss 0.0G | host avail 18.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.21 cpu 12.08 | cgroup 11.5G/16106127360 oom_kill 0 | free scratch 331.1G/45491088i tmp 30.3G/1035746i workspace 331.1G/45491089i | repeat-01 collected 26/26 workers (60588 items) tests 6677 done 5 failed | 26 in flight, oldest 55s gw0 tests/ace/tui/test_plan_decision_ace_render_rail.py::test_compact_verdict_stays_inside_rail_with_stylesheet
................ [278%]
...................................................................[contention-diag] +1013s soak 29p/223t rss 12.3G pss 11.2G swap 0.1G majflt 134 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.0G pss 11.0G, 1 descendant rss 0.1G pss 0.1G | host avail 19.1G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.52 cpu 13.01 | cgroup 11.6G/16106127360 oom_kill 0 | free scratch 331.1G/45490233i tmp 30.3G/1035746i workspace 331.1G/45490233i | repeat-01 collected 26/26 workers (60588 items) tests 6762 done 5 failed | 26 in flight, oldest 48s gw14 tests/ace/tui/test_config_edit_modal_vim_widget.py::test_enter_submits_from_normal_mode
..... [281%]
........................................................................ [284%]
................[contention-diag] +1028s soak 29p/228t rss 12.3G pss 11.2G swap 0.1G majflt 145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.1G pss 11.0G, 1 descendant rss 0.1G pss 0.1G | host avail 18.4G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.56 cpu 13.12 | cgroup 11.6G/16106127360 oom_kill 0 | free scratch 331.1G/45489208i tmp 30.3G/1035746i workspace 331.1G/45489208i | repeat-01 collected 26/26 workers (60588 items) tests 6854 done 5 failed | 26 in flight, oldest 42s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
........................................................ [287%]
..............................................[contention-diag] +1044s soak 29p/229t rss 12.3G pss 11.2G swap 0.1G majflt 152 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.1G pss 11.0G, 1 descendant rss 0.1G pss 0.1G | host avail 19.4G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.09 cpu 13.34 | cgroup 11.6G/16106127360 oom_kill 0 | free scratch 331.0G/45488070i tmp 30.3G/1035745i workspace 331.0G/45488070i | repeat-01 collected 26/26 workers (60588 items) tests 6958 done 5 failed | 26 in flight, oldest 57s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
.......................... [290%]
........................................................................ [293%]
...................................................................[contention-diag] +1059s soak 28p/216t rss 12.3G pss 11.2G swap 0.1G majflt 172 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.1G pss 11.1G | host avail 18.5G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.16 cpu 12.09 | cgroup 11.6G/16106127360 oom_kill 0 | free scratch 331.0G/45486886i tmp 30.3G/1035746i workspace 331.0G/45486886i | repeat-01 collected 26/26 workers (60588 items) tests 7120 done 5 failed | 26 in flight, oldest 52s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
..... [296%]
........................................................................ [299%]
..................................................[contention-diag] +1074s soak 29p/229t rss 12.3G pss 11.2G swap 0.1G majflt 179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.1G pss 11.1G, 1 descendant rss 0.0G pss 0.0G | host avail 18.2G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.03 cpu 12.2 | cgroup 11.6G/16106127360 oom_kill 0 | free scratch 331.0G/45485873i tmp 30.3G/1035746i workspace 331.0G/45485873i | repeat-01 collected 26/26 workers (60588 items) tests 7248 done 5 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
...................... [302%]
.......................................[contention-diag] +1090s soak 29p/225t rss 12.4G pss 11.2G swap 0.1G majflt 183 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.1G pss 11.1G, 1 descendant rss 0.1G pss 0.0G | host avail 18.4G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.44 cpu 11.49 | cgroup 11.6G/16106127360 oom_kill 0 | free scratch 331.6G/45512750i tmp 30.3G/1035746i workspace 331.6G/45512750i | repeat-01 collected 26/26 workers (60588 items) tests 7306 done 5 failed | 26 in flight, oldest 49s gw20 tests/ace/tui/test_link_follow_seam.py::test_closed_phase_follow_selects_without_hanging
................................. [305%]
........................................................................ [308%]
..........................................[contention-diag] +1105s soak 28p/221t rss 12.3G pss 11.2G swap 0.1G majflt 197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.2G pss 11.1G | host avail 21.3G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.41 cpu 11.88 | cgroup 11.6G/16106127360 oom_kill 0 | free scratch 331.6G/45511917i tmp 30.3G/1035746i workspace 331.6G/45511917i | scratch used 0.2G in 24707 entries | repeat-01 collected 26/26 workers (60588 items) tests 7440 done 5 failed | 26 in flight, oldest 59s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
.............................. [311%]
........................................................................ [314%]
...................[contention-diag] +1121s soak 28p/225t rss 12.4G pss 11.2G swap 0.2G majflt 235 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.2G pss 11.1G | host avail 21.1G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.04 cpu 12.32 | cgroup 11.6G/16106127360 oom_kill 0 | free scratch 331.6G/45510892i tmp 30.3G/1035746i workspace 331.6G/45510892i | repeat-01 collected 26/26 workers (60588 items) tests 7579 done 5 failed | 26 in flight, oldest 75s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_subtab_keys_wrap_and_gate_hidden_pr_actions
...........................................[contention-diag] +1136s soak 28p/221t rss 12.4G pss 11.3G swap 0.2G majflt 257 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.2G pss 11.1G | host avail 19.5G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.3 cpu 12.69 | cgroup 11.6G/16106127360 oom_kill 0 | free scratch 331.6G/45510177i tmp 30.3G/1035746i workspace 331.6G/45510177i | repeat-01 collected 26/26 workers (60588 items) tests 7622 done 5 failed | 26 in flight, oldest 56s gw4 tests/ace/tui/test_artifacts_files_loading.py::test_cursor_survives_refresh_and_jk_has_no_highlight_echoes
.......... [317%]
...............[contention-diag] +1151s soak 38p/232t rss 12.5G pss 11.3G swap 0.2G majflt 261 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.2G pss 11.1G, 10 descendant rss 0.1G pss 0.0G | host avail 21.0G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.4 cpu 12.72 | cgroup 11.7G/16106127360 oom_kill 0 | free scratch 331.6G/45509695i tmp 30.3G/1035746i workspace 331.6G/45509695i | repeat-01 collected 26/26 workers (60588 items) tests 7640 done 5 failed | 26 in flight, oldest 55s gw12 tests/ace/tui/test_artifacts_plans_interactions.py::test_plans_pane_navigates_three_document_sections
........[contention-diag] +1167s soak 38p/246t rss 12.5G pss 11.3G swap 0.2G majflt 265 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.2G pss 11.1G, 10 descendant rss 0.1G pss 0.0G | host avail 20.5G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.85 cpu 13.4 | cgroup 11.7G/16106127360 oom_kill 0 | free scratch 331.6G/45509844i tmp 30.3G/1035746i workspace 331.6G/45509844i | repeat-01 collected 26/26 workers (60588 items) tests 7653 done 5 failed | 26 in flight, oldest 53s gw25 tests/ace/tui/test_plugins_browser_pane_install.py::test_plugins_pane_install_marked_set_takes_batch_path
..............................................[contention-diag] +1182s soak 38p/245t rss 12.5G pss 11.3G swap 0.2G majflt 272 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.2G pss 11.1G, 10 descendant rss 0.1G pss 0.0G | host avail 24.3G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.52 cpu 14.27 | cgroup 11.7G/16106127360 oom_kill 0 | free scratch 331.4G/45508138i tmp 30.3G/1035747i workspace 331.4G/45508138i | repeat-01 collected 26/26 workers (60588 items) tests 7701 done 5 failed | 26 in flight, oldest 65s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
... [320%]
........................................................................ [323%]
[contention-diag] +1197s soak 39p/236t rss 12.5G pss 11.3G swap 0.2G majflt 293 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.3G pss 11.2G, 11 descendant rss 0.1G pss 0.1G | host avail 23.8G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.47 cpu 13.65 | cgroup 11.7G/16106127360 oom_kill 0 | free scratch 331.4G/45507644i tmp 30.3G/1035747i workspace 331.4G/45507644i | repeat-01 collected 26/26 workers (60588 items) tests 7771 done 5 failed | 26 in flight, oldest 81s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
........................................................................ [326%]
.......................................................[contention-diag] +1213s soak 39p/238t rss 12.7G pss 11.5G swap 0.2G majflt 358 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.3G pss 11.2G, 11 descendant rss 0.3G pss 0.2G | host avail 24.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.55 cpu 15.51 | cgroup 11.9G/16106127360 oom_kill 0 | free scratch 331.4G/45507034i tmp 30.3G/1035747i workspace 331.4G/45507034i | repeat-01 collected 26/26 workers (60588 items) tests 7902 done 5 failed | 26 in flight, oldest 96s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
................. [329%]
.....................[contention-diag] +1228s soak 39p/227t rss 12.6G pss 11.4G swap 0.2G majflt 310 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.3G pss 11.2G, 11 descendant rss 0.1G pss 0.1G | host avail 24.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.95 cpu 15.35 | cgroup 11.8G/16106127360 oom_kill 0 | free scratch 331.4G/45506265i tmp 30.3G/1035747i workspace 331.4G/45506265i | scratch used 0.2G in 26712 entries | repeat-01 collected 26/26 workers (60588 items) tests 7940 done 5 failed | 26 in flight, oldest 111s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
..................[contention-diag] +1243s soak 38p/242t rss 12.6G pss 11.4G swap 0.2G majflt 313 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.3G pss 11.2G, 10 descendant rss 0.1G pss 0.0G | host avail 23.5G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.37/0.37 io 3.02 cpu 13.45 | cgroup 11.8G/16106127360 oom_kill 0 | free scratch 331.4G/45505702i tmp 30.3G/1035747i workspace 331.4G/45505702i | repeat-01 collected 26/26 workers (60588 items) tests 7956 done 5 failed | 26 in flight, oldest 53s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
...............[contention-diag] +1259s soak 38p/237t rss 12.6G pss 11.4G swap 0.2G majflt 322 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.3G pss 11.2G, 10 descendant rss 0.1G pss 0.0G | host avail 24.0G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 3.22 cpu 15.53 | cgroup 11.8G/16106127360 oom_kill 0 | free scratch 331.4G/45505149i tmp 30.3G/1035747i workspace 331.4G/45505149i | repeat-01 collected 26/26 workers (60588 items) tests 7973 done 5 failed | 26 in flight, oldest 68s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................. [332%]
........................................................................ [335%]
........................[contention-diag] +1274s soak 28p/230t rss 12.5G pss 11.4G swap 0.2G majflt 332 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.3G pss 11.2G | host avail 22.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 2.65 cpu 14.12 | cgroup 11.8G/16106127360 oom_kill 0 | free scratch 331.4G/45504634i tmp 30.3G/1035747i workspace 331.4G/45504634i | repeat-01 collected 26/26 workers (60588 items) tests 8085 done 5 failed | 26 in flight, oldest 83s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
................................................ [338%]
...[contention-diag] +1289s soak 28p/222t rss 12.5G pss 11.4G swap 0.2G majflt 342 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.4G pss 11.2G | host avail 22.0G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.24 cpu 14.82 | cgroup 11.8G/16106127360 oom_kill 0 | free scratch 331.4G/45502486i tmp 30.3G/1035745i workspace 331.4G/45502486i | repeat-01 collected 26/26 workers (60588 items) tests 8137 done 5 failed | 26 in flight, oldest 99s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
..................................................................... [341%]
....................[contention-diag] +1305s soak 30p/214t rss 12.6G pss 11.4G swap 0.2G majflt 376 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.4G pss 11.3G, 2 descendant rss 0.0G pss 0.0G | host avail 27.5G/62.7G swapfree 52.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.65 cpu 17.17 | cgroup 11.8G/16106127360 oom_kill 0 | free scratch 331.2G/45501617i tmp 30.3G/1035747i workspace 331.2G/45501617i | repeat-01 collected 26/26 workers (60588 items) tests 8228 done 5 failed | 26 in flight, oldest 114s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................................... [344%]
........................................................................ [347%]
......................................................................[contention-diag] +1320s soak 29p/220t rss 12.6G pss 11.4G swap 0.2G majflt 401 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.4G pss 11.3G, 1 descendant rss 0.0G pss 0.0G | host avail 26.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.89 cpu 16.42 | cgroup 11.8G/16106127360 oom_kill 0 | free scratch 331.2G/45501137i tmp 30.3G/1035747i workspace 331.2G/45501137i | repeat-01 collected 26/26 workers (60588 items) tests 8413 done 5 failed | 26 in flight, oldest 129s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.. [350%]
........................................................................ [353%]
....................................................[contention-diag] +1335s soak 29p/228t rss 12.6G pss 11.5G swap 0.2G majflt 423 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.5G pss 11.3G, 1 descendant rss 0.0G pss 0.0G | host avail 24.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.91 cpu 12.12 | cgroup 11.9G/16106127360 oom_kill 0 | free scratch 331.3G/45500322i tmp 30.3G/1035747i workspace 331.3G/45500322i | repeat-01 collected 26/26 workers (60588 items) tests 8533 done 5 failed | 25 in flight, oldest 145s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................... [356%]
........................................................................ [359%]
......................................................................[contention-diag] +1351s soak 29p/217t rss 12.6G pss 11.4G swap 0.2G majflt 458 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.4G pss 11.3G, 1 descendant rss 0.0G pss 0.0G | host avail 23.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.09 cpu 12.81 | cgroup 11.9G/16106127360 oom_kill 0 | free scratch 331.3G/45499187i tmp 30.3G/1035747i workspace 331.3G/45499187i | scratch used 0.2G in 29094 entries | repeat-01 collected 26/26 workers (60588 items) tests 8709 done 5 failed | 26 in flight, oldest 160s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.. [362%]
........................................................................ [365%]
.........................[contention-diag] +1366s soak 28p/224t rss 12.6G pss 11.5G swap 0.2G majflt 479 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.5G pss 11.3G | host avail 22.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.91 cpu 12.23 | cgroup 11.9G/16106127360 oom_kill 0 | free scratch 331.3G/45497209i tmp 30.3G/1035747i workspace 331.3G/45497209i | repeat-01 collected 26/26 workers (60588 items) tests 8801 done 5 failed | 25 in flight, oldest 51s gw25 tests/ace/tui/test_plugins_browser_pane_install.py::test_plugins_pane_install_no_change_refreshes_without_restart
............................................... [368%]
...[contention-diag] +1382s soak 30p/227t rss 12.7G pss 11.5G swap 0.2G majflt 498 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.5G pss 11.4G, 2 descendant rss 0.0G pss 0.0G | host avail 20.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 4.43 cpu 12.14 | cgroup 11.9G/16106127360 oom_kill 0 | free scratch 331.3G/45495642i tmp 30.3G/1035746i workspace 331.3G/45495642i | repeat-01 collected 26/26 workers (60588 items) tests 8857 done 5 failed | 26 in flight, oldest 46s gw23 tests/ace/tui/test_config_pane_widget_commit.py::test_config_pane_dirty_source_uses_canonical_commit_prompt
..................................................................... [371%]
...............[contention-diag] +1397s soak 29p/231t rss 12.7G pss 11.5G swap 0.2G majflt 504 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.5G pss 11.4G, 1 descendant rss 0.0G pss 0.0G | host avail 25.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 3.78 cpu 13.36 | cgroup 11.9G/16106127360 oom_kill 0 | free scratch 331.3G/45493923i tmp 30.3G/1035747i workspace 331.3G/45493923i | repeat-01 collected 26/26 workers (60588 items) tests 8943 done 5 failed | 26 in flight, oldest 55s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_browse_navigation_works_on_open_and_after_committing_edit
.............[contention-diag] +1412s soak 29p/223t rss 12.7G pss 11.5G swap 0.2G majflt 778 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.5G pss 11.4G, 1 descendant rss 0.0G pss 0.0G | host avail 24.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.75 cpu 12.6 | cgroup 12.0G/16106127360 oom_kill 0 | free scratch 331.2G/45491349i tmp 30.3G/1035747i workspace 331.2G/45491349i | repeat-01 collected 26/26 workers (60588 items) tests 8955 done 5 failed | 26 in flight, oldest 67s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_collapsed_tribe_rail_title_shows_urgency
............................F...[contention-diag] +1428s soak 28p/220t rss 12.7G pss 11.5G swap 0.2G majflt 541 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.5G pss 11.4G | host avail 23.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.64 cpu 12.18 | cgroup 12.0G/16106127360 oom_kill 0 | free scratch 331.2G/45488758i tmp 30.3G/1035748i workspace 331.2G/45488758i | repeat-01 collected 26/26 workers (60588 items) tests 8988 done 6 failed | 26 in flight, oldest 68s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............ [374%]
.........[contention-diag] +1443s soak 28p/226t rss 12.7G pss 11.6G swap 0.2G majflt 553 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.6G pss 11.4G | host avail 24.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 14.37 | cgroup 12.0G/16106127360 oom_kill 0 | free scratch 331.2G/45486556i tmp 30.3G/1035748i workspace 331.2G/45486556i | repeat-01 collected 26/26 workers (60588 items) tests 9008 done 6 failed | 26 in flight, oldest 84s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................................................... [377%]
....................................[contention-diag] +1458s soak 28p/234t rss 12.7G pss 11.6G swap 0.2G majflt 567 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.6G pss 11.4G | host avail 25.1G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 15.57 | cgroup 12.0G/16106127360 oom_kill 0 | free scratch 331.2G/45485965i tmp 30.3G/1035748i workspace 331.2G/45485965i | repeat-01 collected 26/26 workers (60588 items) tests 9104 done 6 failed | 26 in flight, oldest 99s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
.................................... [380%]
.......[contention-diag] +1474s soak 28p/231t rss 12.8G pss 11.6G swap 0.2G majflt 575 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.6G pss 11.4G | host avail 25.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 18.21 | cgroup 12.1G/16106127360 oom_kill 0 | free scratch 331.2G/45485378i tmp 30.3G/1035748i workspace 331.2G/45485378i | scratch used 0.2G in 30827 entries | repeat-01 collected 26/26 workers (60588 items) tests 9148 done 6 failed | 26 in flight, oldest 114s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................................................[contention-diag] +1489s soak 28p/234t rss 12.8G pss 11.6G swap 0.2G majflt 716 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.6G pss 11.5G | host avail 24.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.98 | cgroup 12.1G/16106127360 oom_kill 0 | free scratch 331.2G/45484756i tmp 30.3G/1035748i workspace 331.2G/45484756i | repeat-01 collected 26/26 workers (60588 items) tests 9211 done 6 failed | 26 in flight, oldest 130s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..... [383%]
.........[contention-diag] +1505s soak 28p/235t rss 12.8G pss 11.6G swap 0.2G majflt 724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.6G pss 11.5G | host avail 24.1G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.77 | cgroup 12.1G/16106127360 oom_kill 0 | free scratch 331.2G/45484261i tmp 30.3G/1035748i workspace 331.2G/45484261i | repeat-01 collected 26/26 workers (60588 items) tests 9222 done 6 failed | 26 in flight, oldest 145s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
............................................................... [386%]
............................................[contention-diag] +1520s soak 28p/208t rss 12.8G pss 11.6G swap 0.2G majflt 731 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.6G pss 11.5G | host avail 23.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 14.68 | cgroup 12.1G/16106127360 oom_kill 0 | free scratch 331.2G/45482922i tmp 30.3G/1035746i workspace 331.2G/45482921i | repeat-01 collected 26/26 workers (60588 items) tests 9327 done 6 failed | 26 in flight, oldest 134s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............................ [389%]
........................................................................ [392%]
........................[contention-diag] +1535s soak 29p/228t rss 12.8G pss 11.6G swap 0.2G majflt 744 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.6G pss 11.5G, 1 descendant rss 0.0G pss 0.0G | host avail 24.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 15.55 | cgroup 12.1G/16106127360 oom_kill 0 | free scratch 331.2G/45482405i tmp 30.3G/1035746i workspace 331.2G/45482405i | repeat-01 collected 26/26 workers (60588 items) tests 9451 done 6 failed | 26 in flight, oldest 149s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................ [395%]
........................................................................ [398%]
......[contention-diag] +1551s soak 28p/231t rss 12.8G pss 11.7G swap 0.2G majflt 758 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.7G pss 11.5G | host avail 22.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.71 | cgroup 12.2G/16106127360 oom_kill 0 | free scratch 331.2G/45481873i tmp 30.3G/1035745i workspace 331.2G/45481873i | repeat-01 collected 26/26 workers (60588 items) tests 9581 done 6 failed | 26 in flight, oldest 164s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.........................................[contention-diag] +1566s soak 28p/227t rss 12.8G pss 11.7G swap 0.2G majflt 766 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 12.7G pss 11.5G | host avail 23.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 15.56 | cgroup 12.2G/16106127360 oom_kill 0 | free scratch 331.2G/45481325i tmp 30.3G/1035745i workspace 331.2G/45481325i | repeat-01 collected 26/26 workers (60588 items) tests 9623 done 6 failed | 26 in flight, oldest 180s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......................... [401%]
........................................................................ [404%]
..................................[contention-diag] +1582s soak 28p/222t rss 12.9G pss 11.7G swap 0.2G majflt 777 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.5G | host avail 23.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.26 cpu 16.61 | cgroup 12.2G/16106127360 oom_kill 0 | free scratch 331.1G/45480501i tmp 30.3G/1035745i workspace 331.1G/45480501i | repeat-01 collected 26/26 workers (60588 items) tests 9752 done 6 failed | 26 in flight, oldest 195s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................... [407%]
.................................[contention-diag] +1597s soak 30p/237t rss 12.9G pss 11.7G swap 0.2G majflt 785 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.5G, 2 descendant rss 0.0G pss 0.0G | host avail 23.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.36 cpu 16.68 | cgroup 12.2G/16106127360 oom_kill 0 | free scratch 331.1G/45480503i tmp 30.3G/1035743i workspace 331.1G/45480503i | scratch used 0.2G in 33052 entries | repeat-01 collected 26/26 workers (60588 items) tests 9821 done 6 failed | 26 in flight, oldest 210s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...............................[contention-diag] +1612s soak 28p/226t rss 12.9G pss 11.7G swap 0.2G majflt 798 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G | host avail 24.1G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 16.97 | cgroup 12.2G/16106127360 oom_kill 0 | free scratch 331.2G/45487056i tmp 30.3G/1035743i workspace 331.2G/45487056i | repeat-01 collected 26/26 workers (60588 items) tests 9853 done 6 failed | 26 in flight, oldest 226s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
........ [410%]
..................[contention-diag] +1628s soak 29p/218t rss 12.9G pss 11.8G swap 0.2G majflt 802 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 1 descendant rss 0.1G pss 0.0G | host avail 21.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 13.56 | cgroup 12.3G/16106127360 oom_kill 0 | free scratch 331.2G/45489487i tmp 30.3G/1035743i workspace 331.2G/45489487i | repeat-01 collected 26/26 workers (60588 items) tests 9879 done 6 failed | 26 in flight, oldest 241s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................................... [413%]
........................................................................ [416%]
..........................[contention-diag] +1643s soak 29p/228t rss 12.9G pss 11.7G swap 0.2G majflt 818 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G, 1 descendant rss 0.0G pss 0.0G | host avail 22.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 15.59 | cgroup 12.3G/16106127360 oom_kill 0 | free scratch 331.2G/45488590i tmp 30.3G/1035743i workspace 331.2G/45488591i | repeat-01 collected 26/26 workers (60588 items) tests 10029 done 6 failed | 25 in flight, oldest 257s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............................................. [419%]
........................................................................ [422%]
........................................................................ [425%]
......[contention-diag] +1658s soak 28p/223t rss 12.9G pss 11.7G swap 0.2G majflt 844 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G | host avail 23.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 14.76 | cgroup 12.3G/16106127360 oom_kill 0 | free scratch 331.2G/45488205i tmp 30.3G/1035743i workspace 331.2G/45488205i | repeat-01 collected 26/26 workers (60588 items) tests 10222 done 6 failed | 26 in flight, oldest 272s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................................. [428%]
......................................................[contention-diag] +1674s soak 28p/230t rss 12.9G pss 11.7G swap 0.2G majflt 859 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.6G | host avail 24.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 16.77 | cgroup 12.3G/16106127360 oom_kill 0 | free scratch 331.2G/45486713i tmp 30.3G/1035743i workspace 331.2G/45486713i | repeat-01 collected 26/26 workers (60588 items) tests 10346 done 6 failed | 26 in flight, oldest 287s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................. [431%]
........................[contention-diag] +1689s soak 28p/234t rss 12.9G pss 11.7G swap 0.2G majflt 884 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G | host avail 23.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.25 cpu 15.69 | cgroup 12.3G/16106127360 oom_kill 0 | free scratch 331.2G/45485777i tmp 30.3G/1035743i workspace 331.2G/45485777i | repeat-01 collected 26/26 workers (60588 items) tests 10389 done 6 failed | 26 in flight, oldest 303s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................................ [434%]
.........[contention-diag] +1704s soak 28p/229t rss 12.9G pss 11.8G swap 0.2G majflt 894 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G | host avail 24.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 15.69 | cgroup 12.3G/16106127360 oom_kill 0 | free scratch 331.2G/45485083i tmp 30.3G/1035743i workspace 331.2G/45485083i | repeat-01 collected 26/26 workers (60588 items) tests 10449 done 6 failed | 26 in flight, oldest 52s gw18 tests/ace/tui/test_live_reply_follow_mounted_reply.py::test_gated_muse_stream_reaches_mounted_reply_before_terminal
............................................................... [437%]
....................[contention-diag] +1720s soak 30p/241t rss 13.0G pss 11.8G swap 0.2G majflt 909 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 2 descendant rss 0.0G pss 0.0G | host avail 24.1G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.76 | cgroup 12.3G/16106127360 oom_kill 0 | free scratch 331.3G/45491176i tmp 30.3G/1035743i workspace 331.3G/45491176i | scratch used 0.2G in 35492 entries | repeat-01 collected 26/26 workers (60588 items) tests 10528 done 6 failed | 26 in flight, oldest 67s gw18 tests/ace/tui/test_live_reply_follow_mounted_reply.py::test_gated_muse_stream_reaches_mounted_reply_before_terminal
.................................................... [440%]
.......................................................[contention-diag] +1736s soak 29p/227t rss 13.0G pss 11.8G swap 0.2G majflt 984 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 1 descendant rss 0.0G pss 0.0G | host avail 24.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.21 | cgroup 12.3G/16106127360 oom_kill 0 | free scratch 331.2G/45489998i tmp 30.3G/1035736i workspace 331.2G/45489998i | repeat-01 collected 26/26 workers (60588 items) tests 10638 done 6 failed | 26 in flight, oldest 81s gw3 tests/ace/tui/test_live_reply_follow_mounted_workflow.py::test_gated_muse_stream_reaches_mounted_workflow_step_reply
................. [443%]
........................................................................ [446%]
............................................................[contention-diag] +1751s soak 29p/235t rss 13.0G pss 11.8G swap 0.2G majflt 993 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 1 descendant rss 0.0G pss 0.0G | host avail 22.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.83 | cgroup 12.4G/16106127360 oom_kill 0 | free scratch 331.2G/45488432i tmp 30.3G/1035719i workspace 331.2G/45488432i | repeat-01 collected 26/26 workers (60588 items) tests 10783 done 6 failed | 26 in flight, oldest 47s gw17 tests/ace/tui/test_projects_pane_current_project_seed.py::test_display_marks_row_summary_and_detail_after_resolve
............ [449%]
........................................................................ [452%]
.........................................[contention-diag] +1766s soak 30p/230t rss 13.0G pss 11.8G swap 0.2G majflt 1092 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.6G, 2 descendant rss 0.0G pss 0.0G | host avail 22.3G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.26 cpu 16.75 | cgroup 12.4G/16106127360 oom_kill 0 | free scratch 331.2G/45487197i tmp 30.3G/1035714i workspace 331.2G/45487197i | repeat-01 collected 26/26 workers (60588 items) tests 10899 done 6 failed | 26 in flight, oldest 56s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
.......................F....... [455%]
........................................................................ [458%]
........................................................................ [461%]
........................................................[contention-diag] +1782s soak 29p/233t rss 13.0G pss 11.9G swap 0.2G majflt 1112 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.7G, 1 descendant rss 0.0G pss 0.0G | host avail 24.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 18.05 | cgroup 12.4G/16106127360 oom_kill 0 | free scratch 331.3G/45488318i tmp 30.3G/1035714i workspace 331.3G/45488318i | repeat-01 collected 26/26 workers (60588 items) tests 11136 done 7 failed | 26 in flight, oldest 72s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
................ [464%]
........................................................................ [467%]
.[contention-diag] +1797s soak 29p/239t rss 13.1G pss 11.9G swap 0.2G majflt 1122 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.7G, 1 descendant rss 0.0G pss 0.0G | host avail 23.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 18.57 | cgroup 12.4G/16106127360 oom_kill 0 | free scratch 331.2G/45487668i tmp 30.3G/1035712i workspace 331.2G/45487668i | repeat-01 collected 26/26 workers (60588 items) tests 11230 done 7 failed | 26 in flight, oldest 52s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
....................................................................... [470%]
...............................[contention-diag] +1812s soak 28p/222t rss 13.1G pss 11.9G swap 0.2G majflt 1126 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.7G | host avail 23.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 18.72 | cgroup 12.4G/16106127360 oom_kill 0 | free scratch 331.2G/45486953i tmp 30.3G/1035709i workspace 331.2G/45486953i | repeat-01 collected 26/26 workers (60588 items) tests 11322 done 7 failed | 25 in flight, oldest 67s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
......................................... [473%]
..........[contention-diag] +1828s soak 29p/241t rss 13.1G pss 11.9G swap 0.2G majflt 1144 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.7G, 1 descendant rss 0.0G pss 0.0G | host avail 23.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.81 | cgroup 12.4G/16106127360 oom_kill 0 | free scratch 331.2G/45486301i tmp 30.3G/1035706i workspace 331.2G/45486301i | repeat-01 collected 26/26 workers (60588 items) tests 11384 done 7 failed | 26 in flight, oldest 83s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.............................................................. [476%]
................................................[contention-diag] +1843s soak 31p/229t rss 13.1G pss 11.9G swap 0.2G majflt 1148 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.7G, 3 descendant rss 0.0G pss 0.0G | host avail 22.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.55 | cgroup 12.5G/16106127360 oom_kill 0 | free scratch 331.2G/45485685i tmp 30.3G/1035706i workspace 331.2G/45485685i | scratch used 0.2G in 38795 entries | repeat-01 collected 26/26 workers (60588 items) tests 11488 done 7 failed | 26 in flight, oldest 58s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
........................ [479%]
....................[contention-diag] +1859s soak 32p/228t rss 13.1G pss 11.9G swap 0.2G majflt 1153 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.7G, 4 descendant rss 0.0G pss 0.0G | host avail 23.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.03 | cgroup 12.5G/16106127360 oom_kill 0 | free scratch 331.3G/45485779i tmp 30.3G/1035705i workspace 331.3G/45485779i | repeat-01 collected 26/26 workers (60588 items) tests 11535 done 7 failed | 26 in flight, oldest 74s gw6 tests/ace/tui/test_live_reply_follow_mounted_session.py::test_gated_muse_stream_reaches_mounted_session_current_turn_reply
............................F....................... [482%]
.[contention-diag] +1874s soak 29p/225t rss 13.2G pss 12.0G swap 0.2G majflt 1163 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.8G, 1 descendant rss 0.0G pss 0.0G | host avail 22.2G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 15.68 | cgroup 12.5G/16106127360 oom_kill 0 | free scratch 331.1G/45483464i tmp 30.3G/1035705i workspace 331.1G/45483464i | repeat-01 collected 26/26 workers (60588 items) tests 11590 done 8 failed | 26 in flight, oldest 64s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
........................................................[contention-diag] +1890s soak 28p/221t rss 13.1G pss 11.9G swap 0.2G majflt 1169 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.7G | host avail 23.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 13.3 | cgroup 12.5G/16106127360 oom_kill 0 | free scratch 330.5G/45481507i tmp 30.3G/1035702i workspace 330.5G/45481507i | repeat-01 collected 26/26 workers (60588 items) tests 11647 done 8 failed | 26 in flight, oldest 54s gw22 tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_h_l_collapse_expand_and_descend
............... [485%]
..................................[contention-diag] +1905s soak 28p/213t rss 13.1G pss 11.9G swap 0.2G majflt 1188 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.7G | host avail 22.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 16.27 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 330.5G/45480847i tmp 30.3G/1035704i workspace 330.5G/45480847i | repeat-01 collected 26/26 workers (60588 items) tests 11698 done 8 failed | 26 in flight, oldest 69s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
...................................... [488%]
..............................................[contention-diag] +1920s soak 31p/232t rss 13.1G pss 11.9G swap 0.2G majflt 1194 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.8G, 3 descendant rss 0.0G pss 0.0G | host avail 21.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 18.23 | cgroup 12.5G/16106127360 oom_kill 0 | free scratch 330.5G/45479461i tmp 30.3G/1035704i workspace 330.5G/45479461i | repeat-01 collected 26/26 workers (60588 items) tests 11780 done 8 failed | 26 in flight, oldest 84s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
.......................... [491%]
...................................................[contention-diag] +1936s soak 29p/211t rss 13.1G pss 11.9G swap 0.2G majflt 1229 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G, 1 descendant rss 0.0G pss 0.0G | host avail 20.2G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.22/0.0 io 0.0 cpu 14.35 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 330.5G/45478056i tmp 30.3G/1035704i workspace 330.5G/45478056i | repeat-01 collected 26/26 workers (60588 items) tests 11858 done 8 failed | 26 in flight, oldest 99s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
..................... [494%]
................................[contention-diag] +1951s soak 31p/224t rss 13.2G pss 12.0G swap 0.2G majflt 1256 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.8G, 3 descendant rss 0.1G pss 0.0G | host avail 18.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.19/0.14 io 0.14 cpu 15.31 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 330.5G/45477574i tmp 30.3G/1035704i workspace 330.5G/45477574i | repeat-01 collected 26/26 workers (60588 items) tests 11910 done 8 failed | 26 in flight, oldest 59s gw14 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
........................................ [497%]
........................................................................ [500%]
........................................................................ [503%]
.......................[contention-diag] +1966s soak 29p/216t rss 13.2G pss 11.9G swap 0.2G majflt 1285 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G, 1 descendant rss 0.0G pss 0.0G | host avail 18.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 0.15 cpu 15.56 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 330.0G/45476425i tmp 30.3G/1035704i workspace 330.0G/45476425i | scratch used 0.2G in 41120 entries | repeat-01 collected 26/26 workers (60588 items) tests 12110 done 8 failed | 26 in flight, oldest 75s gw14 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
................................................. [506%]
........................................................[contention-diag] +1982s soak 29p/212t rss 13.2G pss 11.9G swap 0.2G majflt 1321 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G, 1 descendant rss 0.0G pss 0.0G | host avail 22.2G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 15.55 | cgroup 12.5G/16106127360 oom_kill 0 | free scratch 329.7G/45474617i tmp 30.3G/1035704i workspace 329.7G/45474617i | repeat-01 collected 26/26 workers (60588 items) tests 12221 done 8 failed | 26 in flight, oldest 54s gw2 tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_opens_preview_modal
................ [509%]
.......................................................................[contention-diag] +1998s soak 29p/213t rss 13.2G pss 12.0G swap 0.2G majflt 1335 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G, 1 descendant rss 0.0G pss 0.0G | host avail 24.1G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 16.34 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 329.7G/45471346i tmp 30.3G/1035704i workspace 329.7G/45471346i | repeat-01 collected 26/26 workers (60588 items) tests 12310 done 8 failed | 26 in flight, oldest 53s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
. [512%]
...........................................................[contention-diag] +2013s soak 30p/219t rss 13.2G pss 12.0G swap 0.2G majflt 1353 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G, 2 descendant rss 0.0G pss 0.0G | host avail 25.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 20.64 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 329.7G/45454405i tmp 30.3G/1035704i workspace 329.7G/45454405i | repeat-01 collected 26/26 workers (60588 items) tests 12367 done 8 failed | 26 in flight, oldest 56s gw23 tests/ace/tui/test_link_follow_planner.py::test_phase_context_rewrite_selects_and_restores
............. [515%]
........................................................................ [518%]
........................................................................ [521%]
................[contention-diag] +2028s soak 28p/217t rss 13.2G pss 12.0G swap 0.2G majflt 1370 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G | host avail 25.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 21.93 | cgroup 12.5G/16106127360 oom_kill 0 | free scratch 329.7G/45453455i tmp 30.3G/1035705i workspace 329.7G/45453455i | repeat-01 collected 26/26 workers (60588 items) tests 12538 done 8 failed | 26 in flight, oldest 54s gw11 tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_is_noop_while_filter_input_has_focus
........................................................ [524%]
........................................................................ [527%]
........................................................................ [530%]
........[contention-diag] +2044s soak 29p/211t rss 13.2G pss 12.0G swap 0.2G majflt 1376 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G, 1 descendant rss 0.0G pss 0.0G | host avail 24.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 19.06 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 329.7G/45452555i tmp 30.3G/1035705i workspace 329.7G/45452555i | repeat-01 collected 26/26 workers (60588 items) tests 12733 done 8 failed | 24 in flight, oldest 50s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_close_each_of_three_panels_keeps_textual_focus
................................................................ [533%]
......s................................................................. [536%]
........................................................................ [539%]
....[contention-diag] +2059s soak 28p/216t rss 13.2G pss 12.0G swap 0.2G majflt 1396 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G | host avail 24.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.91 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 329.6G/45451560i tmp 30.3G/1035705i workspace 329.6G/45451560i | repeat-01 collected 26/26 workers (60588 items) tests 12961 done 8 failed | 26 in flight, oldest 52s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
.................................................................... [542%]
............................[contention-diag] +2074s soak 28p/217t rss 13.2G pss 12.0G swap 0.2G majflt 1405 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G | host avail 24.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.12 cpu 18.82 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 329.7G/45452160i tmp 30.3G/1035705i workspace 329.7G/45452160i | repeat-01 collected 26/26 workers (60588 items) tests 13056 done 8 failed | 26 in flight, oldest 68s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
............................................ [545%]
...[contention-diag] +2090s soak 29p/229t rss 13.2G pss 12.0G swap 0.2G majflt 1471 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G, 1 descendant rss 0.0G pss 0.0G | host avail 24.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 21.5 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 329.7G/45451540i tmp 30.3G/1035705i workspace 329.7G/45451540i | scratch used 0.3G in 44160 entries | repeat-01 collected 26/26 workers (60588 items) tests 13101 done 8 failed | 26 in flight, oldest 48s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_filter_brackets_cycle_subtabs_and_tab_switches_main_tab
..................................................................... [548%]
..........[contention-diag] +2106s soak 32p/239t rss 13.3G pss 12.0G swap 0.2G majflt 1623 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.1G pss 11.9G, 4 descendant rss 0.0G pss 0.0G | host avail 23.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.2 | cgroup 12.6G/16106127360 oom_kill 0 | free scratch 329.7G/45450853i tmp 30.3G/1035705i workspace 329.7G/45450853i | repeat-01 collected 26/26 workers (60588 items) tests 13178 done 8 failed | 26 in flight, oldest 55s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_real_deck_keys_reach_actions_on_two_and_three_panels
.............................................................. [551%]
...............................................................[contention-diag] +2121s soak 32p/248t rss 13.4G pss 12.1G swap 0.2G majflt 1678 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.1G pss 11.9G, 4 descendant rss 0.1G pss 0.1G | host avail 22.1G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 15.8 | cgroup 12.7G/16106127360 oom_kill 0 | free scratch 329.7G/45449943i tmp 30.3G/1035705i workspace 329.7G/45449943i | repeat-01 collected 26/26 workers (60588 items) tests 13300 done 8 failed | 26 in flight, oldest 65s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
......... [554%]
........................................................................ [557%]
......................................................................F. [560%]
[contention-diag] +2136s soak 32p/224t rss 13.4G pss 12.1G swap 0.2G majflt 1688 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G, 4 descendant rss 0.1G pss 0.1G | host avail 24.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 18.04 | cgroup 12.9G/16106127360 oom_kill 0 | free scratch 329.7G/45448995i tmp 30.3G/1035704i workspace 329.7G/45448995i | repeat-01 collected 26/26 workers (60588 items) tests 13460 done 9 failed | 26 in flight, oldest 80s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
.........................................[contention-diag] +2152s soak 31p/211t rss 13.3G pss 12.0G swap 0.2G majflt 1691 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.0G pss 11.8G, 3 descendant rss 0.0G pss 0.0G | host avail 23.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 18.89 | cgroup 12.7G/16106127360 oom_kill 0 | free scratch 329.7G/45449285i tmp 30.3G/1035704i workspace 329.7G/45449285i | repeat-01 collected 26/26 workers (60588 items) tests 13503 done 9 failed | 26 in flight, oldest 54s gw13 tests/ace/tui/test_config_pane_widget.py::test_config_pane_modified_only_toggle
............................... [563%]
........................................................................ [566%]
.[contention-diag] +2167s soak 32p/235t rss 13.3G pss 12.1G swap 0.2G majflt 1706 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.1G pss 11.9G, 4 descendant rss 0.1G pss 0.0G | host avail 23.2G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 18.97 | cgroup 12.7G/16106127360 oom_kill 0 | free scratch 329.7G/45448582i tmp 30.3G/1035703i workspace 329.7G/45448582i | repeat-01 collected 26/26 workers (60588 items) tests 13601 done 9 failed | 26 in flight, oldest 61s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
....................................................................... [569%]
........................................................................ [572%]
.........[contention-diag] +2182s soak 31p/227t rss 13.3G pss 12.1G swap 0.2G majflt 1725 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.1G pss 11.9G, 3 descendant rss 0.1G pss 0.0G | host avail 22.2G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.03 | cgroup 12.7G/16106127360 oom_kill 0 | free scratch 329.7G/45447259i tmp 30.3G/1035703i workspace 329.7G/45447259i | repeat-01 collected 26/26 workers (60588 items) tests 13740 done 9 failed | 26 in flight, oldest 77s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............................................................... [575%]
........................................................................ [578%]
...............................................................[contention-diag] +2198s soak 32p/227t rss 13.3G pss 12.1G swap 0.2G majflt 1738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.1G pss 11.9G, 4 descendant rss 0.0G pss 0.0G | host avail 22.3G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 15.33 | cgroup 12.8G/16106127360 oom_kill 0 | free scratch 329.7G/45447094i tmp 30.3G/1035659i workspace 329.7G/45447094i | repeat-01 collected 26/26 workers (60588 items) tests 13957 done 9 failed | 26 in flight, oldest 92s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
......... [581%]
........................................................................ [584%]
......................[contention-diag] +2213s soak 32p/217t rss 13.3G pss 12.1G swap 0.2G majflt 1748 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.1G pss 11.9G, 4 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.26 cpu 14.75 | cgroup 12.9G/16106127360 oom_kill 0 | free scratch 329.7G/45446426i tmp 30.3G/1035596i workspace 329.7G/45446426i | scratch used 0.3G in 47169 entries | repeat-01 collected 26/26 workers (60588 items) tests 14049 done 9 failed | 25 in flight, oldest 108s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.................................................. [587%]
........................................................................ [590%]
.............................................................[contention-diag] +2229s soak 28p/208t rss 13.3G pss 12.1G swap 0.2G majflt 1757 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.1G pss 11.9G | host avail 22.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.14 cpu 13.82 | cgroup 12.7G/16106127360 oom_kill 0 | free scratch 329.7G/45445607i tmp 30.3G/1035591i workspace 329.7G/45445607i | repeat-01 collected 26/26 workers (60588 items) tests 14234 done 9 failed | 26 in flight, oldest 65s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_deck_close_each_and_erase_through_keys
........... [593%]
........................................................................ [596%]
........................................................................ [599%]
...F..............................................................[contention-diag] +2245s soak 31p/219t rss 13.4G pss 12.1G swap 0.2G majflt 1812 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.1G pss 11.9G, 3 descendant rss 0.0G pss 0.0G | host avail 21.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.03 cpu 13.17 | cgroup 12.8G/16106127360 oom_kill 0 | free scratch 329.7G/45444369i tmp 30.3G/1035548i workspace 329.7G/45444369i | repeat-01 collected 26/26 workers (60588 items) tests 14464 done 10 failed | 26 in flight, oldest 56s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_digits_type_in_an_opened_filter
...... [602%]
..........................................................F............. [605%]
........................................................................ [608%]
........F.........[contention-diag] +2260s soak 29p/220t rss 13.4G pss 12.1G swap 0.2G majflt 1825 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.1G pss 11.9G, 1 descendant rss 0.0G pss 0.0G | host avail 25.3G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.66 cpu 15.01 | cgroup 12.8G/16106127360 oom_kill 0 | free scratch 329.7G/45442854i tmp 30.3G/1035575i workspace 329.7G/45442854i | repeat-01 collected 26/26 workers (60588 items) tests 14620 done 11 failed | 26 in flight, oldest 45s gw11 tests/ace/tui/test_launch_context_bar.py::test_full_cluster_reads_label_chip_separator_label_chip
...................................................... [611%]
........................................................................ [614%]
....................................F.........[contention-diag] +2275s soak 31p/230t rss 13.4G pss 12.2G swap 0.2G majflt 1850 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.2G pss 12.0G, 3 descendant rss 0.0G pss 0.0G | host avail 23.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.61 cpu 14.44 | cgroup 12.9G/16106127360 oom_kill 0 | free scratch 329.6G/45441443i tmp 30.3G/1035573i workspace 329.6G/45441443i | repeat-01 collected 26/26 workers (60588 items) tests 14804 done 13 failed | 26 in flight, oldest 49s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
.......................... [617%]
.............................................................F.......... [620%]
........................................................................ [623%]
......................................[contention-diag] +2291s soak 32p/218t rss 13.6G pss 12.3G swap 0.2G majflt 1865 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.2G pss 12.0G, 4 descendant rss 0.2G pss 0.1G | host avail 25.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.33 cpu 16.88 | cgroup 13.0G/16106127360 oom_kill 0 | free scratch 329.6G/45439960i tmp 30.3G/1035559i workspace 329.6G/45439960i | repeat-01 collected 26/26 workers (60588 items) tests 15000 done 14 failed | 25 in flight, oldest 65s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
...........F...................... [626%]
........................................................................ [629%]
..............................................F......................... [632%]
...........[contention-diag] +2306s soak 31p/199t rss 13.5G pss 12.3G swap 0.2G majflt 1874 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.2G pss 12.0G, 3 descendant rss 0.1G pss 0.1G | host avail 24.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.7 cpu 18.35 | cgroup 13.0G/16106127360 oom_kill 0 | free scratch 329.6G/45439067i tmp 30.3G/1035558i workspace 329.6G/45439067i | repeat-01 collected 26/26 workers (60588 items) tests 15195 done 16 failed | 26 in flight, oldest 58s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
..........F.................................................. [635%]
...........................................................F..........[contention-diag] +2322s soak 30p/215t rss 13.5G pss 12.2G swap 0.2G majflt 1886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.2G pss 12.0G, 2 descendant rss 0.1G pss 0.1G | host avail 22.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 16.3 | cgroup 13.0G/16106127360 oom_kill 0 | free scratch 329.6G/45438669i tmp 30.3G/1035665i workspace 329.6G/45438669i | repeat-01 collected 26/26 workers (60588 items) tests 15333 done 18 failed | 26 in flight, oldest 74s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.. [638%]
.............................F.......................................... [641%]
........................................................................ [644%]
.......F............[contention-diag] +2337s soak 31p/221t rss 13.6G pss 12.3G swap 0.2G majflt 1893 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.2G pss 12.0G, 3 descendant rss 0.1G pss 0.1G | host avail 23.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.34 cpu 16.58 | cgroup 13.1G/16106127360 oom_kill 0 | free scratch 329.6G/45437715i tmp 30.3G/1035590i workspace 329.6G/45437715i | scratch used 0.3G in 53918 entries | repeat-01 collected 26/26 workers (60588 items) tests 15477 done 19 failed | 25 in flight, oldest 89s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................... [647%]
........................................................................ [650%]
..................................[contention-diag] +2353s soak 31p/230t rss 13.6G pss 12.3G swap 0.2G majflt 1997 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.0G, 3 descendant rss 0.2G pss 0.1G | host avail 22.9G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.23 cpu 16.68 | cgroup 13.1G/16106127360 oom_kill 0 | free scratch 329.6G/45436459i tmp 30.3G/1035585i workspace 329.6G/45436459i | repeat-01 collected 26/26 workers (60588 items) tests 15655 done 20 failed | 26 in flight, oldest 105s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
......F............................... [653%]
........................................................................ [656%]
.............................................F.......................... [659%]
............................................................[contention-diag] +2368s soak 33p/224t rss 13.7G pss 12.3G swap 0.2G majflt 2031 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.0G, 5 descendant rss 0.3G pss 0.1G | host avail 23.3G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.05 cpu 18.41 | cgroup 13.0G/16106127360 oom_kill 0 | free scratch 329.6G/45435613i tmp 30.3G/1035585i workspace 329.6G/45435613i | repeat-01 collected 26/26 workers (60588 items) tests 15888 done 22 failed | 26 in flight, oldest 120s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
............ [662%]
........................................................................ [665%]
.....................F.................................................. [668%]
..............................[contention-diag] +2384s soak 36p/211t rss 13.5G pss 12.3G swap 0.2G majflt 2067 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.1G, 8 descendant rss 0.1G pss 0.0G | host avail 24.2G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.28 cpu 19.24 | cgroup 13.0G/16106127360 oom_kill 0 | free scratch 329.6G/45434265i tmp 30.3G/1035585i workspace 329.6G/45434265i | repeat-01 collected 26/26 workers (60588 items) tests 16081 done 23 failed | 25 in flight, oldest 136s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.......................................... [671%]
........................................................................ [674%]
........................................................................ [677%]
........................................................................ [680%]
........................................................................ [683%]
........................................................................ [686%]
..[contention-diag] +2399s soak 32p/214t rss 13.6G pss 12.3G swap 0.2G majflt 2108 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.1G, 4 descendant rss 0.1G pss 0.1G | host avail 23.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.41 cpu 18.58 | cgroup 13.1G/16106127360 oom_kill 0 | free scratch 329.6G/45433293i tmp 30.3G/1035584i workspace 329.6G/45433293i | repeat-01 collected 26/26 workers (60588 items) tests 16484 done 23 failed | 26 in flight, oldest 151s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
...................................................................... [689%]
........................................................................ [692%]
........................................................................ [695%]
........................................................................ [698%]
.......[contention-diag] +2414s soak 32p/212t rss 13.6G pss 12.3G swap 0.2G majflt 2142 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.1G, 4 descendant rss 0.1G pss 0.1G | host avail 24.1G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.15 cpu 19.27 | cgroup 13.1G/16106127360 oom_kill 0 | free scratch 329.6G/45434690i tmp 30.3G/1035584i workspace 329.6G/45434690i | repeat-01 collected 26/26 workers (60588 items) tests 16778 done 23 failed | 26 in flight, oldest 99s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
................................................................. [701%]
..............................................................[contention-diag] +2430s soak 36p/214t rss 13.7G pss 12.4G swap 0.2G majflt 2154 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.1G, 8 descendant rss 0.1G pss 0.1G | host avail 23.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.63 cpu 19.72 | cgroup 13.1G/16106127360 oom_kill 0 | free scratch 329.6G/45433151i tmp 30.3G/1035583i workspace 329.6G/45433151i | repeat-01 collected 26/26 workers (60588 items) tests 16909 done 23 failed | 26 in flight, oldest 114s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.......... [704%]
........................................................................ [707%]
........................................................................ [710%]
........................................................................ [713%]
....................[contention-diag] +2445s soak 36p/220t rss 13.9G pss 12.6G swap 0.2G majflt 3115 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.1G, 8 descendant rss 0.4G pss 0.3G | host avail 23.5G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.52 cpu 19.18 | cgroup 13.3G/16106127360 oom_kill 0 | free scratch 329.6G/45430687i tmp 30.3G/1035583i workspace 329.6G/45430687i | repeat-01 collected 26/26 workers (60588 items) tests 17141 done 23 failed | 26 in flight, oldest 129s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
.................................................... [716%]
........................................................................ [719%]
........................................................................ [722%]
............................[contention-diag] +2460s soak 36p/208t rss 13.8G pss 12.5G swap 0.2G majflt 2192 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.1G, 8 descendant rss 0.2G pss 0.2G | host avail 22.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.0 cpu 18.81 | cgroup 13.4G/16106127360 oom_kill 0 | free scratch 329.6G/45427444i tmp 30.3G/1035583i workspace 329.6G/45427444i | scratch used 0.3G in 57727 entries | repeat-01 collected 26/26 workers (60588 items) tests 17355 done 23 failed | 26 in flight, oldest 145s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
............................................ [725%]
....................F................................................... [728%]
........................................................................ [731%]
.....................................................[contention-diag] +2476s soak 37p/208t rss 13.6G pss 12.3G swap 0.2G majflt 2213 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.1G, 9 descendant rss 0.1G pss 0.0G | host avail 21.7G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.77 cpu 17.45 | cgroup 13.2G/16106127360 oom_kill 0 | free scratch 329.5G/45425250i tmp 30.3G/1035583i workspace 329.5G/45425250i | repeat-01 collected 26/26 workers (60588 items) tests 17612 done 24 failed | 26 in flight, oldest 161s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
................... [734%]
........................................................................ [737%]
................................................[contention-diag] +2492s soak 34p/230t rss 13.6G pss 12.3G swap 0.2G majflt 2232 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.3G pss 12.1G, 6 descendant rss 0.0G pss 0.0G | host avail 22.8G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.55 cpu 18.75 | cgroup 13.2G/16106127360 oom_kill 0 | free scratch 329.5G/45422887i tmp 30.3G/1035583i workspace 329.5G/45422887i | repeat-01 collected 26/26 workers (60588 items) tests 17758 done 24 failed | 26 in flight, oldest 176s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
........................ [740%]
........................................................................ [743%]
............................[contention-diag] +2507s soak 37p/215t rss 13.7G pss 12.2G swap 0.2G majflt 2240 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 11.9G, 9 descendant rss 0.1G pss 0.1G | host avail 23.2G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.43 cpu 18.08 | cgroup 13.4G/16106127360 oom_kill 0 | free scratch 329.6G/45420681i tmp 30.3G/1035583i workspace 329.6G/45420681i | repeat-01 collected 26/26 workers (60588 items) tests 17877 done 24 failed | 26 in flight, oldest 99s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................................ [746%]
........................................................................ [749%]
..................................................[contention-diag] +2522s soak 35p/209t rss 13.6G pss 12.3G swap 0.2G majflt 2255 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 7 descendant rss 0.0G pss 0.0G | host avail 24.0G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 1.09 cpu 18.06 | cgroup 13.4G/16106127360 oom_kill 0 | free scratch 329.5G/45419376i tmp 30.3G/1035583i workspace 329.5G/45419376i | repeat-01 collected 26/26 workers (60588 items) tests 18046 done 24 failed | 26 in flight, oldest 63s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cancel_saves_once_submit_path_quiet
...................... [752%]
........................................................................ [755%]
........................................................................ [758%]
..............................[contention-diag] +2538s soak 36p/214t rss 13.8G pss 12.5G swap 0.2G majflt 2263 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 8 descendant rss 0.2G pss 0.2G | host avail 22.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.35 cpu 18.0 | cgroup 13.6G/16106127360 oom_kill 0 | free scratch 329.5G/45418154i tmp 30.3G/1035583i workspace 329.5G/45418154i | repeat-01 collected 26/26 workers (60588 items) tests 18243 done 24 failed | 26 in flight, oldest 78s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cancel_saves_once_submit_path_quiet
................F......................... [761%]
.................F......................................[contention-diag] +2553s soak 37p/215t rss 13.8G pss 12.5G swap 0.2G majflt 2274 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 9 descendant rss 0.2G pss 0.2G | host avail 23.6G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.23 cpu 16.16 | cgroup 13.5G/16106127360 oom_kill 0 | free scratch 329.5G/45416078i tmp 30.3G/1035583i workspace 329.5G/45416078i | repeat-01 collected 26/26 workers (60588 items) tests 18335 done 26 failed | 26 in flight, oldest 62s gw23 tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui
.F.............. [764%]
..F..........................F.............[contention-diag] +2568s soak 36p/224t rss 13.7G pss 12.4G swap 0.2G majflt 2366 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 8 descendant rss 0.1G pss 0.0G | host avail 25.4G/62.7G swapfree 53.2G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 2.12 cpu 15.63 | cgroup 13.4G/16106127360 oom_kill 0 | free scratch 329.6G/45432703i tmp 30.3G/1035583i workspace 329.6G/45432703i | repeat-01 collected 26/26 workers (60588 items) tests 18394 done 29 failed | 26 in flight, oldest 77s gw23 tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui
............F.............F.. [767%]
................................................................s....... [770%]
...................................................................F.... [773%]
........................................................................ [776%]
.........................[contention-diag] +2584s soak 35p/227t rss 13.7G pss 12.4G swap 0.2G majflt 2447 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 7 descendant rss 0.0G pss 0.0G | host avail 30.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 1.04 cpu 17.26 | cgroup 13.5G/16106127360 oom_kill 0 | free scratch 329.5G/45430170i tmp 30.3G/1035584i workspace 329.5G/45430170i | scratch used 0.3G in 61649 entries | repeat-01 collected 26/26 workers (60588 items) tests 18656 done 32 failed | 26 in flight, oldest 68s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.....F..............s....s..................... [779%]
........................................................................ [782%]
...F.......................................s............................ [785%]
.........F.....................[contention-diag] +2600s soak 34p/221t rss 13.7G pss 12.4G swap 0.2G majflt 2481 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.1G, 6 descendant rss 0.1G pss 0.1G | host avail 28.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.68 cpu 18.39 | cgroup 13.6G/16106127360 oom_kill 0 | free scratch 329.5G/45428237i tmp 30.3G/1035584i workspace 329.5G/45428237i | repeat-01 collected 26/26 workers (60588 items) tests 18885 done 35 failed | 26 in flight, oldest 84s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
..........................F.............. [788%]
.........................F.............................................. [791%]
................[contention-diag] +2615s soak 38p/218t rss 13.9G pss 12.6G swap 0.2G majflt 2491 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.2G, 10 descendant rss 0.3G pss 0.2G | host avail 28.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.61 cpu 21.31 | cgroup 13.8G/16106127360 oom_kill 0 | free scratch 329.5G/45425694i tmp 30.3G/1035584i workspace 329.5G/45425694i | repeat-01 collected 26/26 workers (60588 items) tests 19013 done 37 failed | 26 in flight, oldest 99s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
........................F............................... [794%]
.F.....F.....................................................F.......... [797%]
.......[contention-diag] +2631s soak 31p/199t rss 13.7G pss 12.4G swap 0.2G majflt 2499 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.2G, 3 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.22 cpu 20.66 | cgroup 13.4G/16106127360 oom_kill 0 | free scratch 329.5G/45424194i tmp 30.3G/1035584i workspace 329.5G/45424194i | repeat-01 collected 26/26 workers (60588 items) tests 19150 done 41 failed | 26 in flight, oldest 64s gw19 tests/ace/tui/test_statistics_view_number_select.py::test_non_digit_cancels_prefix_and_continues_to_modal[q]
................................................................. [800%]
.....F..F............................................................... [803%]
................................[contention-diag] +2646s soak 31p/196t rss 13.7G pss 12.4G swap 0.2G majflt 2529 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.2G, 3 descendant rss 0.1G pss 0.0G | host avail 29.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.27 cpu 22.45 | cgroup 13.5G/16106127360 oom_kill 0 | free scratch 329.5G/45423086i tmp 30.3G/1035584i workspace 329.5G/45423086i | repeat-01 collected 26/26 workers (60588 items) tests 19325 done 43 failed | 25 in flight, oldest 58s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_manual_update_drops_expired_load_freshness
.....................................F.. [806%]
.........................F...F..............F........................... [809%]
..........................F...........................................[contention-diag] +2661s soak 37p/225t rss 13.8G pss 12.5G swap 0.2G majflt 2545 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.2G, 9 descendant rss 0.2G pss 0.1G | host avail 28.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 21.83 | cgroup 13.5G/16106127360 oom_kill 0 | free scratch 329.5G/45422402i tmp 30.3G/1035584i workspace 329.5G/45422402i | repeat-01 collected 26/26 workers (60588 items) tests 19501 done 48 failed | 26 in flight, oldest 52s gw1 tests/test_command_palette_e2e.py::test_semicolon_opens_command_palette_from_agents_and_axe_tabs
.. [812%]
..................................................................F..... [815%]
........................................................................ [818%]
...........F............................................................ [821%]
.....................................[contention-diag] +2677s soak 36p/216t rss 13.9G pss 12.5G swap 0.2G majflt 2567 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 8 descendant rss 0.2G pss 0.1G | host avail 28.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 21.92 | cgroup 13.5G/16106127360 oom_kill 0 | free scratch 329.6G/45429938i tmp 30.3G/1035706i workspace 329.6G/45429938i | repeat-01 collected 26/26 workers (60588 items) tests 19749 done 50 failed | 25 in flight, oldest 67s gw1 tests/test_command_palette_e2e.py::test_semicolon_opens_command_palette_from_agents_and_axe_tabs
...............................F... [824%]
........................................................................ [827%]
..........F............................................................. [830%]
..............................................F......................... [833%]
..[contention-diag] +2692s soak 36p/221t rss 13.9G pss 12.6G swap 0.2G majflt 2584 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 8 descendant rss 0.2G pss 0.1G | host avail 27.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 17.89 | cgroup 13.5G/16106127360 oom_kill 0 | free scratch 329.5G/45429230i tmp 30.3G/1035706i workspace 329.5G/45429230i | repeat-01 collected 26/26 workers (60588 items) tests 20014 done 53 failed | 26 in flight, oldest 65s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_quit_with_spare_leaves_no_tasks
...........................................................F.......... [836%]
.....................................................................F.. [839%]
............................................................[contention-diag] +2708s soak 39p/226t rss 13.9G pss 12.5G swap 0.2G majflt 2609 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 11 descendant rss 0.2G pss 0.1G | host avail 26.6G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.83 cpu 15.85 | cgroup 13.5G/16106127360 oom_kill 0 | free scratch 329.5G/45428520i tmp 30.3G/1035706i workspace 329.5G/45428522i | scratch used 0.4G in 67731 entries | repeat-01 collected 26/26 workers (60588 items) tests 20211 done 55 failed | 26 in flight, oldest 51s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_reload_clears_freshness_while_in_progress
............ [842%]
........................................................................ [845%]
...........[contention-diag] +2724s soak 34p/231t rss 13.9G pss 12.5G swap 0.2G majflt 2616 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 6 descendant rss 0.1G pss 0.1G | host avail 28.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.75 cpu 19.87 | cgroup 13.6G/16106127360 oom_kill 0 | free scratch 329.5G/45428036i tmp 30.3G/1035706i workspace 329.5G/45428036i | repeat-01 collected 26/26 workers (60588 items) tests 20314 done 55 failed | 26 in flight, oldest 67s gw12 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_live_tick_keeps_ctrl_j_card
............................................................. [848%]
.F...................................................................... [851%]
.................................................[contention-diag] +2739s soak 38p/218t rss 13.8G pss 12.5G swap 0.2G majflt 2630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 10 descendant rss 0.1G pss 0.1G | host avail 27.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 19.92 | cgroup 13.7G/16106127360 oom_kill 0 | free scratch 329.5G/45428165i tmp 30.3G/1035706i workspace 329.5G/45428165i | repeat-01 collected 26/26 workers (60588 items) tests 20483 done 56 failed | 26 in flight, oldest 82s gw12 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_live_tick_keeps_ctrl_j_card
....................... [854%]
........................................................................ [857%]
........................................................................ [860%]
..........[contention-diag] +2754s soak 39p/217t rss 14.0G pss 12.6G swap 0.2G majflt 2647 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 11 descendant rss 0.2G pss 0.2G | host avail 28.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 22.05 | cgroup 13.7G/16106127360 oom_kill 0 | free scratch 329.5G/45426929i tmp 30.3G/1035705i workspace 329.5G/45426929i | repeat-01 collected 26/26 workers (60588 items) tests 20670 done 56 failed | 25 in flight, oldest 97s gw12 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_live_tick_keeps_ctrl_j_card
.............................................................. [863%]
........................................................................ [866%]
........................................................................ [869%]
........................................[contention-diag] +2770s soak 34p/214t rss 14.0G pss 12.6G swap 0.2G majflt 2664 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 6 descendant rss 0.2G pss 0.2G | host avail 29.1G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.32 cpu 20.67 | cgroup 13.7G/16106127360 oom_kill 0 | free scratch 329.5G/45426273i tmp 30.3G/1035705i workspace 329.5G/45426273i | repeat-01 collected 26/26 workers (60588 items) tests 20918 done 56 failed | 26 in flight, oldest 56s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_macro_focus_picker_all_clear_key_and_cancel
................................ [872%]
........................................................................ [875%]
...............[contention-diag] +2785s soak 30p/211t rss 13.8G pss 12.5G swap 0.2G majflt 2674 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 2 descendant rss 0.1G pss 0.0G | host avail 26.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 17.75 | cgroup 13.6G/16106127360 oom_kill 0 | free scratch 329.5G/45425996i tmp 30.3G/1035705i workspace 329.5G/45425996i | repeat-01 collected 26/26 workers (60588 items) tests 21036 done 56 failed | 26 in flight, oldest 51s gw16 tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_confirm_executes_and_restarts
......................................................... [878%]
........................................................................ [881%]
........................................................................ [884%]
........................................................................ [887%]
.....................................................[contention-diag] +2800s soak 33p/224t rss 13.8G pss 12.5G swap 0.2G majflt 2687 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 5 descendant rss 0.1G pss 0.0G | host avail 24.2G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 15.81 | cgroup 13.7G/16106127360 oom_kill 0 | free scratch 329.5G/45425415i tmp 30.3G/1035705i workspace 329.5G/45425415i | repeat-01 collected 26/26 workers (60588 items) tests 21354 done 56 failed | 25 in flight, oldest 62s gw14 tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
................... [890%]
.............................F.......................................... [893%]
........................................................................ [896%]
......................................................[contention-diag] +2816s soak 31p/220t rss 13.8G pss 12.4G swap 0.2G majflt 2730 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 3 descendant rss 0.0G pss 0.0G | host avail 27.5G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 18.11 | cgroup 13.5G/16106127360 oom_kill 0 | free scratch 329.5G/45424593i tmp 30.3G/1035705i workspace 329.5G/45424593i | repeat-01 collected 26/26 workers (60588 items) tests 21579 done 57 failed | 26 in flight, oldest 64s gw18 tests/ace/tui/test_statistics_footprint.py::test_footprint_card_reloads_after_row_move
.................. [899%]
........................................................................ [902%]
........................................................................ [905%]
..............................[contention-diag] +2831s soak 34p/221t rss 13.8G pss 12.5G swap 0.2G majflt 2742 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 6 descendant rss 0.0G pss 0.0G | host avail 28.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.2 cpu 19.86 | cgroup 13.6G/16106127360 oom_kill 0 | free scratch 329.5G/45423929i tmp 30.3G/1035705i workspace 329.5G/45423929i | scratch used 0.4G in 72096 entries | repeat-01 collected 26/26 workers (60588 items) tests 21748 done 57 failed | 26 in flight, oldest 69s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_config_center_cycles_all_tabs
.......................................... [908%]
........................................................................ [911%]
........................................................................ [914%]
........................................................................ [917%]
........F..................................[contention-diag] +2847s soak 29p/212t rss 13.8G pss 12.5G swap 0.2G majflt 2764 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 1 descendant rss 0.0G pss 0.0G | host avail 28.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.26 cpu 18.37 | cgroup 13.5G/16106127360 oom_kill 0 | free scratch 329.5G/45422981i tmp 30.3G/1035702i workspace 329.5G/45422981i | repeat-01 collected 26/26 workers (60588 items) tests 22065 done 58 failed | 26 in flight, oldest 85s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_config_center_cycles_all_tabs
............................. [920%]
........................................................................ [923%]
........................................................................ [926%]
........................................................................ [929%]
........................................................................ [932%]
...........[contention-diag] +2863s soak 35p/220t rss 13.9G pss 12.5G swap 0.2G majflt 2779 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 7 descendant rss 0.1G pss 0.1G | host avail 26.4G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 18.91 | cgroup 13.6G/16106127360 oom_kill 0 | free scratch 329.5G/45421503i tmp 30.3G/1035702i workspace 329.5G/45421503i | repeat-01 collected 26/26 workers (60588 items) tests 22367 done 58 failed | 26 in flight, oldest 96s gw12 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
............................................................. [935%]
........................................................................ [938%]
........................................................................ [941%]
.......[contention-diag] +2878s soak 32p/204t rss 13.9G pss 12.5G swap 0.2G majflt 2834 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 4 descendant rss 0.1G pss 0.1G | host avail 24.3G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.64 cpu 17.88 | cgroup 13.6G/16106127360 oom_kill 0 | free scratch 329.5G/45420848i tmp 30.3G/1035702i workspace 329.5G/45420848i | repeat-01 collected 26/26 workers (60588 items) tests 22606 done 58 failed | 26 in flight, oldest 112s gw12 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
................................................................. [944%]
........................................................................ [947%]
.....................................................F.................. [950%]
.....[contention-diag] +2894s soak 34p/195t rss 13.9G pss 12.5G swap 0.2G majflt 2853 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.2G, 6 descendant rss 0.1G pss 0.0G | host avail 20.4G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 17.14 | cgroup 13.6G/16106127360 oom_kill 0 | free scratch 329.5G/45419874i tmp 30.3G/1035702i workspace 329.5G/45419874i | repeat-01 collected 26/26 workers (60588 items) tests 22823 done 59 failed | 26 in flight, oldest 48s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_overview_revalidation_tick_never_paints_loading
................................................................... [953%]
........................................................................ [956%]
........................................................................ [959%]
..............................................................[contention-diag] +2909s soak 35p/194t rss 14.0G pss 12.6G swap 0.2G majflt 2875 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.6G pss 12.3G, 7 descendant rss 0.2G pss 0.1G | host avail 21.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 17.66 | cgroup 13.8G/16106127360 oom_kill 0 | free scratch 329.5G/45419378i tmp 30.3G/1035700i workspace 329.5G/45419378i | repeat-01 collected 26/26 workers (60588 items) tests 23099 done 59 failed | 26 in flight, oldest 49s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
.......... [962%]
........................................................................ [965%]
........................................................................ [968%]
...................................................[contention-diag] +2924s soak 34p/200t rss 14.0G pss 12.7G swap 0.2G majflt 2899 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.6G pss 12.3G, 6 descendant rss 0.2G pss 0.2G | host avail 17.2G/62.7G swapfree 54.1G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.32 cpu 16.97 | cgroup 13.8G/16106127360 oom_kill 0 | free scratch 329.5G/45420780i tmp 30.3G/1035700i workspace 329.5G/45420780i | repeat-01 collected 26/26 workers (60588 items) tests 23301 done 59 failed | 26 in flight, oldest 64s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
..................... [971%]
........................................................................ [974%]
........................................................................ [977%]
....................[contention-diag] +2940s soak 36p/192t rss 14.0G pss 12.6G swap 0.2G majflt 2915 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.6G pss 12.3G, 8 descendant rss 0.2G pss 0.1G | host avail 16.1G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.58 cpu 15.44 | cgroup 13.7G/16106127360 oom_kill 0 | free scratch 329.5G/45420223i tmp 30.3G/1035700i workspace 329.5G/45420223i | repeat-01 collected 26/26 workers (60588 items) tests 23489 done 59 failed | 26 in flight, oldest 80s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_modal_tab_switch_keys_change_tab_and_refresh_content
.................................................... [980%]
........................................................................ [983%]
........................................................................ [986%]
........................................................................ [989%]
[contention-diag] +2955s soak 34p/196t rss 14.1G pss 12.7G swap 0.2G majflt 2933 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.6G pss 12.3G, 6 descendant rss 0.2G pss 0.1G | host avail 15.1G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 14.71 | cgroup 13.7G/16106127360 oom_kill 0 | free scratch 329.5G/45419750i tmp 30.3G/1035700i workspace 329.5G/45419750i | scratch used 0.2G in 33823 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 23712 done 59 failed | 26 in flight, oldest 88s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
........................................................................ [992%]
................................................[contention-diag] +2973s soak 35p/197t rss 14.1G pss 12.7G swap 0.2G majflt 3000 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.7G pss 12.4G, 7 descendant rss 0.2G pss 0.1G | host avail 24.9G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 15.79 | cgroup 13.8G/16106127360 oom_kill 0 | free scratch 329.5G/45419206i tmp 30.3G/1035700i workspace 329.5G/45419206i | repeat-01 collected 26/26 workers (60588 items) tests 23878 done 59 failed | 26 in flight, oldest 106s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
........................ [995%]
.................................[contention-diag] +2988s soak 39p/195t rss 14.2G pss 12.8G swap 0.2G majflt 3031 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.8G pss 12.5G, 11 descendant rss 0.2G pss 0.1G | host avail 24.5G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 15.85 | cgroup 13.9G/16106127360 oom_kill 0 | free scratch 329.5G/45418832i tmp 30.3G/1035700i workspace 329.5G/45418832i | repeat-01 collected 26/26 workers (60588 items) tests 23937 done 59 failed | 26 in flight, oldest 121s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
....................................... [998%]
....................................................................[contention-diag] +3003s soak 40p/200t rss 14.3G pss 12.9G swap 0.2G majflt 3037 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.8G pss 12.5G, 12 descendant rss 0.3G pss 0.2G | host avail 20.7G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.71 cpu 14.71 | cgroup 14.1G/16106127360 oom_kill 0 | free scratch 329.5G/45418512i tmp 30.3G/1035700i workspace 329.5G/45418512i | repeat-01 collected 26/26 workers (60588 items) tests 24043 done 59 failed | 26 in flight, oldest 137s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
.... [1001%]
........................................................................ [1004%]
.............................F.....................[contention-diag] +3019s soak 40p/192t rss 14.3G pss 12.9G swap 0.2G majflt 3053 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.9G pss 12.6G, 12 descendant rss 0.2G pss 0.1G | host avail 16.4G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 14.54 | cgroup 14.0G/16106127360 oom_kill 0 | free scratch 329.5G/45418111i tmp 30.3G/1035700i workspace 329.5G/45418111i | repeat-01 collected 26/26 workers (60588 items) tests 24167 done 60 failed | 26 in flight, oldest 152s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
..................... [1007%]
........................................................................ [1010%]
........................................................................ [1013%]
..........................................[contention-diag] +3034s soak 32p/175t rss 14.2G pss 12.9G swap 0.2G majflt 3077 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 13.9G pss 12.6G, 4 descendant rss 0.0G pss 0.0G | host avail 17.2G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 16.33 | cgroup 14.0G/16106127360 oom_kill 0 | free scratch 329.5G/45417630i tmp 30.3G/1035700i workspace 329.5G/45417630i | repeat-01 collected 26/26 workers (60588 items) tests 24367 done 60 failed | 26 in flight, oldest 168s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
.............................. [1016%]
........................................................................ [1019%]
........................................................................ [1022%]
........................................................................ [1025%]
........................................................................ [1028%]
.......................................................[contention-diag] +3050s soak 31p/171t rss 14.4G pss 13.0G swap 0.2G majflt 3105 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.0G pss 12.7G, 3 descendant rss 0.0G pss 0.0G | host avail 16.5G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 17.52 | cgroup 14.1G/16106127360 oom_kill 0 | free scratch 329.5G/45416152i tmp 30.3G/1035700i workspace 329.5G/45416151i | repeat-01 collected 26/26 workers (60588 items) tests 24744 done 60 failed | 26 in flight, oldest 183s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
................. [1031%]
........................................................................ [1034%]
........................................................................ [1037%]
........................................................................ [1040%]
...[contention-diag] +3065s soak 31p/181t rss 14.3G pss 13.0G swap 0.2G majflt 3127 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.0G pss 12.7G, 3 descendant rss 0.1G pss 0.0G | host avail 13.6G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.08/0.0 io 0.22 cpu 16.7 | cgroup 14.1G/16106127360 oom_kill 0 | free scratch 329.4G/45415398i tmp 30.3G/1035700i workspace 329.4G/45415398i | repeat-01 collected 26/26 workers (60588 items) tests 24974 done 60 failed | 25 in flight, oldest 199s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
..................................................................... [1043%]
........................................................................ [1046%]
........................................................................ [1049%]
........................................................................ [1052%]
........................................................................ [1055%]
....................................................[contention-diag] +3081s soak 31p/182t rss 14.4G pss 13.1G swap 0.2G majflt 3149 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.0G pss 12.8G, 3 descendant rss 0.1G pss 0.1G | host avail 26.4G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.13/0.0 io 0.04 cpu 17.26 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 329.5G/45415007i tmp 30.3G/1035700i workspace 329.5G/45415007i | scratch used 0.3G in 61045 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 25351 done 60 failed | 25 in flight, oldest 214s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
.................... [1058%]
........................................................................ [1061%]
s....................................................................... [1064%]
........................................................................ [1067%]
........................................................................ [1070%]
......................[contention-diag] +3098s soak 31p/180t rss 14.4G pss 13.1G swap 0.2G majflt 3165 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.1G pss 12.9G, 3 descendant rss 0.0G pss 0.0G | host avail 24.1G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 1.41 cpu 18.56 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 329.9G/45437705i tmp 30.3G/1035696i workspace 329.9G/45437705i | repeat-01 collected 26/26 workers (60588 items) tests 25709 done 60 failed | 25 in flight, oldest 231s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
.................................................. [1073%]
........................................................................ [1076%]
........................................................................ [1079%]
........................................................................ [1082%]
........................................................................ [1085%]
...............................[contention-diag] +3113s soak 31p/173t rss 14.4G pss 13.1G swap 0.2G majflt 3215 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.1G pss 12.8G, 3 descendant rss 0.0G pss 0.0G | host avail 22.5G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 16.76 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 329.7G/45425320i tmp 30.3G/1035696i workspace 329.7G/45425320i | repeat-01 collected 26/26 workers (60588 items) tests 26085 done 60 failed | 26 in flight, oldest 247s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
........F................................ [1088%]
........................................................................ [1091%]
........................................................................ [1094%]
.....................[contention-diag] +3129s soak 30p/176t rss 14.4G pss 13.2G swap 0.2G majflt 3239 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.1G pss 12.9G, 2 descendant rss 0.0G pss 0.0G | host avail 19.2G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 13.24 | cgroup 14.4G/16106127360 oom_kill 0 | free scratch 329.7G/45424301i tmp 30.3G/1035695i workspace 329.7G/45424301i | repeat-01 collected 26/26 workers (60588 items) tests 26298 done 61 failed | 26 in flight, oldest 262s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
................................................... [1097%]
........................................................................ [1100%]
...............................[contention-diag] +3144s soak 32p/195t rss 14.7G pss 13.4G swap 0.2G majflt 3250 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.3G pss 13.0G, 4 descendant rss 0.1G pss 0.1G | host avail 19.3G/62.7G swapfree 54.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.31 cpu 14.4 | cgroup 14.6G/16106127360 oom_kill 0 | free scratch 329.7G/45424289i tmp 30.3G/1035690i workspace 329.7G/45424289i | repeat-01 collected 26/26 workers (60588 items) tests 26455 done 61 failed | 26 in flight, oldest 278s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
......................................... [1103%]
........................................................................ [1106%]
..........................................[contention-diag] +3160s soak 33p/188t rss 14.7G pss 13.3G swap 0.2G majflt 3345 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.3G pss 13.0G, 5 descendant rss 0.1G pss 0.1G | host avail 18.8G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.36 cpu 14.56 | cgroup 14.5G/16106127360 oom_kill 0 | free scratch 329.7G/45423871i tmp 30.3G/1035686i workspace 329.7G/45423871i | repeat-01 collected 26/26 workers (60588 items) tests 26590 done 61 failed | 26 in flight, oldest 293s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
.............................. [1109%]
........................................................................ [1112%]
........................................................................ [1115%]
........................................................................ [1118%]
........................................................................ [1121%]
.......................................[contention-diag] +3175s soak 34p/182t rss 14.6G pss 13.3G swap 0.3G majflt 3393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.2G pss 13.0G, 6 descendant rss 0.1G pss 0.1G | host avail 11.2G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.13/0.13 io 0.88 cpu 12.76 | cgroup 14.5G/16106127360 oom_kill 0 | free scratch 329.7G/45421322i tmp 30.3G/1035686i workspace 329.7G/45421322i | repeat-01 collected 26/26 workers (60588 items) tests 26944 done 61 failed | 25 in flight, oldest 308s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
................................. [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
........................................................................ [1133%]
..........................[contention-diag] +3190s soak 32p/179t rss 14.5G pss 13.3G swap 0.3G majflt 3459 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.2G pss 13.0G, 4 descendant rss 0.1G pss 0.0G | host avail 11.0G/62.7G swapfree 54.0G/64.0G oom_kill +0 | psi10 mem 1.84/1.12 io 2.4 cpu 12.81 | cgroup 14.5G/16106127360 oom_kill 0 | free scratch 329.7G/45421464i tmp 30.3G/1035681i workspace 329.7G/45421464i | repeat-01 collected 26/26 workers (60588 items) tests 27237 done 61 failed | 26 in flight, oldest 324s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
.............................................. [1136%]
....................................................[contention-diag] +3206s soak 37p/187t rss 14.9G pss 13.5G swap 0.3G majflt 3498 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.4G pss 13.2G, 9 descendant rss 0.2G pss 0.1G | host avail 27.3G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.42/0.22 io 1.86 cpu 17.27 | cgroup 14.6G/16106127360 oom_kill 0 | free scratch 329.7G/45421139i tmp 30.3G/1035683i workspace 329.7G/45421139i | scratch used 0.4G in 71718 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 27333 done 61 failed | 26 in flight, oldest 339s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
.................... [1139%]
........................................................................ [1142%]
.....................................................................[contention-diag] +3223s soak 32p/187t rss 14.9G pss 13.6G swap 0.3G majflt 3562 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.4G pss 13.2G, 4 descendant rss 0.2G pss 0.1G | host avail 27.7G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.06/0.03 io 1.32 cpu 20.99 | cgroup 14.7G/16106127360 oom_kill 0 | free scratch 329.7G/45420627i tmp 30.3G/1035684i workspace 329.7G/45420627i | repeat-01 collected 26/26 workers (60588 items) tests 27501 done 61 failed | 26 in flight, oldest 357s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
... [1145%]
.F...................................................................... [1148%]
........................................................................ [1151%]
........................................................................ [1154%]
........................................................................ [1157%]
........................................................................ [1160%]
........................................................................ [1163%]
.........................................................[contention-diag] +3239s soak 35p/190t rss 14.9G pss 13.6G swap 0.3G majflt 3677 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.5G pss 13.2G, 7 descendant rss 0.2G pss 0.1G | host avail 29.1G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.16/0.0 io 1.61 cpu 20.61 | cgroup 14.7G/16106127360 oom_kill 0 | free scratch 329.7G/45419497i tmp 30.3G/1035684i workspace 329.7G/45419497i | repeat-01 collected 26/26 workers (60588 items) tests 27990 done 62 failed | 26 in flight, oldest 372s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
............... [1166%]
........................................................................ [1169%]
........................................................................ [1172%]
........................................................................ [1175%]
.................[contention-diag] +3254s soak 35p/182t rss 15.0G pss 13.7G swap 0.3G majflt 3812 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.5G pss 13.3G, 7 descendant rss 0.2G pss 0.2G | host avail 25.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.28/0.0 io 1.46 cpu 18.83 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.7G/45418728i tmp 30.3G/1035684i workspace 329.7G/45418728i | repeat-01 collected 26/26 workers (60588 items) tests 28237 done 62 failed | 26 in flight, oldest 388s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
....................................................... [1178%]
........................................................................ [1181%]
........................................................................ [1184%]
.....................................[contention-diag] +3270s soak 37p/192t rss 15.4G pss 14.1G swap 0.3G majflt 4013 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.5G, 9 descendant rss 0.4G pss 0.4G | host avail 27.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 1.03/0.0 io 1.59 cpu 20.43 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.6G/45417996i tmp 30.3G/1035684i workspace 329.6G/45417996i | repeat-01 collected 26/26 workers (60588 items) tests 28476 done 62 failed | 26 in flight, oldest 403s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
................................... [1187%]
........................................................................ [1190%]
........................................................................ [1193%]
................................[contention-diag] +3285s soak 34p/194t rss 15.3G pss 14.0G swap 0.4G majflt 4197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.5G, 6 descendant rss 0.3G pss 0.3G | host avail 27.5G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 1.84/0.1 io 0.97 cpu 18.81 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.6G/45417151i tmp 30.3G/1035684i workspace 329.6G/45417151i | repeat-01 collected 26/26 workers (60588 items) tests 28674 done 62 failed | 26 in flight, oldest 418s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
........................................ [1196%]
........................................................................ [1199%]
........................................................................ [1202%]
........................................................................ [1205%]
.........................................[contention-diag] +3300s soak 35p/179t rss 15.3G pss 14.0G swap 0.4G majflt 4336 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.4G, 7 descendant rss 0.3G pss 0.3G | host avail 26.1G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 1.39/0.02 io 1.03 cpu 20.67 | cgroup 14.8G/16106127360 oom_kill 0 | free scratch 329.6G/45414540i tmp 30.3G/1035684i workspace 329.6G/45414540i | repeat-01 collected 26/26 workers (60588 items) tests 28982 done 62 failed | 26 in flight, oldest 434s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
............................... [1208%]
........................................................................ [1211%]
........................................................................ [1214%]
........................................................................ [1217%]
....................[contention-diag] +3316s soak 34p/186t rss 15.4G pss 14.0G swap 0.4G majflt 4660 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.4G, 6 descendant rss 0.4G pss 0.4G | host avail 26.6G/62.7G swapfree 55.4G/64.0G oom_kill +0 | psi10 mem 0.6/0.0 io 0.87 cpu 20.48 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.7G/45414680i tmp 30.3G/1035684i workspace 329.7G/45414680i | repeat-01 collected 26/26 workers (60588 items) tests 29231 done 62 failed | 25 in flight, oldest 449s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
.................................................... [1220%]
........................................................................ [1223%]
........................................................................ [1226%]
........................................................................ [1229%]
........................................................................ [1232%]
...................................................[contention-diag] +3332s soak 37p/187t rss 15.5G pss 14.1G swap 0.4G majflt 4866 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.5G, 9 descendant rss 0.4G pss 0.4G | host avail 26.1G/62.7G swapfree 55.4G/64.0G oom_kill +0 | psi10 mem 0.47/0.0 io 0.59 cpu 17.89 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.6G/45413307i tmp 30.3G/1035684i workspace 329.6G/45413307i | scratch used 0.1G in 26297 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 29600 done 62 failed | 23 in flight, oldest 465s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
..................... [1235%]
........................................................................ [1238%]
........................................................................ [1241%]
........................................................................ [1244%]
........................................................................ [1247%]
..............................................[contention-diag] +3349s soak 37p/187t rss 15.6G pss 14.2G swap 0.5G majflt 5337 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.8G pss 13.5G, 9 descendant rss 0.5G pss 0.4G | host avail 26.2G/62.7G swapfree 55.3G/64.0G oom_kill +0 | psi10 mem 4.43/0.14 io 0.39 cpu 20.32 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.6G/45412502i tmp 30.3G/1035684i workspace 329.6G/45412502i | repeat-01 collected 26/26 workers (60588 items) tests 29977 done 62 failed | 24 in flight, oldest 393s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
.......................... [1250%]
........................................................................ [1253%]
........................................................................ [1256%]
........................................................................ [1259%]
............................................................[contention-diag] +3364s soak 33p/179t rss 15.5G pss 14.2G swap 0.7G majflt 5668 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.8G pss 13.5G, 5 descendant rss 0.5G pss 0.4G | host avail 27.6G/62.7G swapfree 55.1G/64.0G oom_kill +0 | psi10 mem 4.18/0.03 io 0.75 cpu 23.6 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.6G/45411856i tmp 30.3G/1035684i workspace 329.6G/45411856i | repeat-01 collected 26/26 workers (60588 items) tests 30297 done 62 failed | 25 in flight, oldest 408s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
............ [1262%]
........................................................................ [1265%]
........................................................................ [1268%]
........................................................................ [1271%]
........................................................................ [1274%]
..[contention-diag] +3380s soak 33p/183t rss 15.4G pss 14.0G swap 0.9G majflt 7456 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.4G, 5 descendant rss 0.5G pss 0.4G | host avail 27.2G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 5.47/0.0 io 0.49 cpu 20.08 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.6G/45410586i tmp 30.3G/1035679i workspace 329.6G/45410586i | repeat-01 collected 26/26 workers (60588 items) tests 30597 done 62 failed | 25 in flight, oldest 424s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
...................................................................... [1277%]
........................................................................ [1280%]
........................................................................ [1283%]
........................................................................ [1286%]
........................................................................ [1289%]
........................................................................ [1292%]
..................................[contention-diag] +3395s soak 33p/187t rss 15.4G pss 14.0G swap 0.9G majflt 11260 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.4G, 5 descendant rss 0.4G pss 0.4G | host avail 26.2G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 5.93/0.0 io 0.14 cpu 17.63 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.4G/45398468i tmp 30.3G/1035679i workspace 329.4G/45398468i | repeat-01 collected 26/26 workers (60588 items) tests 31061 done 62 failed | 25 in flight, oldest 439s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
...................................... [1295%]
........................................................................ [1298%]
........................................................................ [1301%]
........................................................................ [1304%]
........................................................................ [1307%]
.....[contention-diag] +3411s soak 40p/196t rss 15.7G pss 14.3G swap 0.9G majflt 13240 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.4G, 12 descendant rss 0.8G pss 0.7G | host avail 25.7G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 5.0/0.0 io 0.59 cpu 18.32 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.4G/45397179i tmp 30.3G/1035679i workspace 329.4G/45397179i | repeat-01 collected 26/26 workers (60588 items) tests 31396 done 62 failed | 25 in flight, oldest 455s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
................................................................... [1310%]
........................................................................ [1313%]
........................................................................ [1316%]
................................[contention-diag] +3426s soak 32p/184t rss 15.5G pss 14.1G swap 0.8G majflt 14577 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.4G, 4 descendant rss 0.5G pss 0.5G | host avail 25.8G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 4.47/0.0 io 0.34 cpu 18.37 | cgroup 14.8G/16106127360 oom_kill 0 | free scratch 329.4G/45396181i tmp 30.3G/1035677i workspace 329.4G/45396181i | repeat-01 collected 26/26 workers (60588 items) tests 31628 done 62 failed | 24 in flight, oldest 470s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
........................................ [1319%]
........................................................................ [1322%]
........................................................................ [1325%]
........................................................................ [1328%]
..............................................................[contention-diag] +3442s soak 35p/184t rss 15.8G pss 14.4G swap 0.8G majflt 22139 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.8G pss 13.5G, 7 descendant rss 0.7G pss 0.6G | host avail 24.4G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 5.4/0.0 io 0.37 cpu 18.44 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.4G/45395243i tmp 30.3G/1035679i workspace 329.4G/45395243i | repeat-01 collected 26/26 workers (60588 items) tests 31955 done 62 failed | 25 in flight, oldest 485s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
.......... [1331%]
........................................................................ [1334%]
........................................................................ [1337%]
........................................................................ [1340%]
.........................F......[contention-diag] +3457s soak 33p/177t rss 15.7G pss 14.3G swap 0.8G majflt 23007 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.8G pss 13.5G, 5 descendant rss 0.6G pss 0.5G | host avail 25.3G/62.7G swapfree 54.9G/64.0G oom_kill +0 | psi10 mem 5.38/0.0 io 0.52 cpu 17.49 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.4G/45394124i tmp 30.3G/1035679i workspace 329.4G/45394124i | scratch used 0.1G in 25165 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 32185 done 62 failed | 25 in flight, oldest 501s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
........................................ [1343%]
........................................................................ [1346%]
.F...................................................................... [1349%]
................................[contention-diag] +3475s soak 36p/180t rss 15.7G pss 14.3G swap 1.0G majflt 23385 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.7G pss 13.4G, 8 descendant rss 0.7G pss 0.7G | host avail 23.6G/62.7G swapfree 54.7G/64.0G oom_kill +0 | psi10 mem 3.01/0.0 io 0.39 cpu 15.89 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.4G/45391567i tmp 30.3G/1035679i workspace 329.4G/45391567i | repeat-01 collected 26/26 workers (60588 items) tests 32431 done 64 failed | 25 in flight, oldest 518s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
........................................ [1352%]
........................................................................ [1355%]
........................................................................ [1358%]
........................................................................ [1361%]
........................................................................ [1364%]
...............................[contention-diag] +3490s soak 35p/175t rss 15.5G pss 14.1G swap 1.2G majflt 23954 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 14.5G pss 13.2G, 7 descendant rss 0.8G pss 0.7G | host avail 26.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 2.33/0.0 io 0.4 cpu 16.32 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.3G/45390459i tmp 30.3G/1035679i workspace 329.3G/45390459i | repeat-01 collected 26/26 workers (60588 items) tests 32766 done 64 failed | 25 in flight, oldest 534s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
......................................... [1367%]
........................................................................ [1370%]
........................................................................ [1373%]
........................................................................ [1376%]
........................................................................ [1379%]
.[contention-diag] +3506s soak 39p/179t rss 15.6G pss 14.1G swap 1.3G majflt 24858 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.4G pss 13.1G, 11 descendant rss 0.9G pss 0.8G | host avail 24.1G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 1.11/0.0 io 0.12 cpu 15.67 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.3G/45389073i tmp 30.3G/1035674i workspace 329.3G/45389073i | repeat-01 collected 26/26 workers (60588 items) tests 33119 done 64 failed | 25 in flight, oldest 549s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...........................F........................................... [1382%]
........................................................................ [1385%]
........................................................................ [1388%]
........................................................................ [1391%]
........................................................................ [1394%]
........................................................................ [1397%]
.[contention-diag] +3521s soak 40p/176t rss 15.7G pss 14.2G swap 1.2G majflt 25332 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.4G pss 13.1G, 12 descendant rss 1.0G pss 0.9G | host avail 23.0G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.27/0.0 io 1.1 cpu 14.78 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.3G/45388184i tmp 30.3G/1035661i workspace 329.3G/45388184i | repeat-01 collected 26/26 workers (60588 items) tests 33544 done 65 failed | 23 in flight, oldest 565s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
....................................................................... [1400%]
...................s.................................................... [1403%]
........................................................................ [1406%]
........................................................................ [1409%]
........................................................................ [1412%]
........................................................................ [1415%]
..........[contention-diag] +3536s soak 40p/176t rss 15.9G pss 14.4G swap 1.2G majflt 38141 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.5G pss 13.2G, 12 descendant rss 1.1G pss 1.0G | host avail 25.4G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 0.66/0.6 io 3.29 cpu 17.81 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.3G/45388944i tmp 30.3G/1035660i workspace 329.3G/45388944i | repeat-01 collected 26/26 workers (60588 items) tests 33969 done 65 failed | 25 in flight, oldest 580s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................F............. [1418%]
..............................................................F......... [1421%]
........................................................................ [1424%]
........................................................................ [1427%]
........................................................................ [1430%]
.........[contention-diag] +3552s soak 40p/184t rss 15.9G pss 14.5G swap 1.1G majflt 52043 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.6G pss 13.3G, 12 descendant rss 1.1G pss 0.9G | host avail 26.5G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 5.15/0.12 io 2.32 cpu 22.1 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.3G/45388015i tmp 30.3G/1035660i workspace 329.3G/45388015i | repeat-01 collected 26/26 workers (60588 items) tests 34337 done 67 failed | 25 in flight, oldest 595s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................................... [1433%]
........................................................................ [1436%]
........................................................................ [1439%]
..........[contention-diag] +3567s soak 41p/188t rss 15.8G pss 14.4G swap 1.1G majflt 56171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.6G pss 13.3G, 13 descendant rss 0.9G pss 0.8G | host avail 26.1G/62.7G swapfree 54.4G/64.0G oom_kill +0 | psi10 mem 3.01/0.02 io 1.37 cpu 20.71 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.3G/45386836i tmp 30.3G/1035656i workspace 329.3G/45386836i | repeat-01 collected 26/26 workers (60588 items) tests 34568 done 67 failed | 25 in flight, oldest 611s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.............................................................. [1442%]
........................................................................ [1445%]
........................................................................ [1448%]
........................................................................ [1451%]
........................................................................ [1454%]
[contention-diag] +3583s soak 43p/184t rss 15.8G pss 14.4G swap 1.1G majflt 57155 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.6G pss 13.3G, 15 descendant rss 0.9G pss 0.8G | host avail 25.6G/62.7G swapfree 54.5G/64.0G oom_kill +0 | psi10 mem 0.6/0.0 io 2.42 cpu 16.9 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.4G/45388681i tmp 30.3G/1035656i workspace 329.4G/45388681i | scratch used 0.1G in 21911 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 34851 done 67 failed | 23 in flight, oldest 626s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................................................ [1457%]
........................................................................ [1460%]
........................................................................ [1463%]
........................................................................ [1466%]
...........[contention-diag] +3600s soak 40p/176t rss 15.8G pss 14.3G swap 1.1G majflt 80981 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.6G pss 13.2G, 12 descendant rss 0.9G pss 0.9G | host avail 24.4G/62.7G swapfree 54.3G/64.0G oom_kill +0 | psi10 mem 1.8/0.08 io 2.0 cpu 16.53 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.3G/45387418i tmp 30.3G/1035656i workspace 329.3G/45387418i | repeat-01 collected 26/26 workers (60588 items) tests 35217 done 67 failed | 24 in flight, oldest 644s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................................. [1469%]
........................................................................ [1472%]
........................................................................ [1475%]
........................................................................ [1478%]
........................................................................ [1481%]
.................................................[contention-diag] +3615s soak 38p/175t rss 15.8G pss 14.3G swap 1.3G majflt 83068 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.4G pss 13.1G, 10 descendant rss 1.1G pss 1.0G | host avail 25.0G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 3.58/0.01 io 2.35 cpu 16.23 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.3G/45385976i tmp 30.3G/1035656i workspace 329.3G/45385976i | repeat-01 collected 26/26 workers (60588 items) tests 35614 done 67 failed | 23 in flight, oldest 659s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
....................... [1484%]
........................................................................ [1487%]
........................................................................ [1490%]
........................................................................ [1493%]
........................................................................ [1496%]
........................................................................ [1499%]
......................................[contention-diag] +3631s soak 48p/189t rss 15.7G pss 14.2G swap 1.5G majflt 83700 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.2G pss 12.9G, 20 descendant rss 1.2G pss 1.1G | host avail 25.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 5.18/0.18 io 2.53 cpu 17.82 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.3G/45384372i tmp 30.3G/1035656i workspace 329.3G/45384372i | repeat-01 collected 26/26 workers (60588 items) tests 36032 done 67 failed | 23 in flight, oldest 675s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.................................. [1502%]
..........................................F............................. [1505%]
........................................................................ [1508%]
........................................................................ [1511%]
........................................................................ [1514%]
........................................................................ [1517%]
............................[contention-diag] +3646s soak 44p/182t rss 15.9G pss 14.4G swap 1.5G majflt 84511 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.2G pss 12.9G, 16 descendant rss 1.4G pss 1.2G | host avail 24.3G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 1.04/0.03 io 1.95 cpu 17.91 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.3G/45383049i tmp 30.3G/1035656i workspace 329.3G/45383050i | repeat-01 collected 26/26 workers (60588 items) tests 36441 done 68 failed | 24 in flight, oldest 690s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................ [1520%]
........................................................................ [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
.................................[contention-diag] +3662s soak 41p/183t rss 15.8G pss 14.3G swap 1.8G majflt 85593 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.0G pss 12.6G, 13 descendant rss 1.5G pss 1.4G | host avail 23.1G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 1.88/0.0 io 1.08 cpu 17.04 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.3G/45382029i tmp 30.3G/1035656i workspace 329.3G/45382029i | repeat-01 collected 26/26 workers (60588 items) tests 36749 done 68 failed | 24 in flight, oldest 706s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
....F.................................. [1532%]
........................................................................ [1535%]
........................................................................ [1538%]
........................................................................ [1541%]
............[contention-diag] +3677s soak 40p/175t rss 15.6G pss 14.0G swap 1.8G majflt 85842 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.0G pss 12.7G, 12 descendant rss 1.3G pss 1.1G | host avail 24.8G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.54/0.0 io 0.99 cpu 17.3 | cgroup 14.7G/16106127360 oom_kill 0 | free scratch 329.3G/45380504i tmp 30.3G/1035656i workspace 329.3G/45380504i | repeat-01 collected 26/26 workers (60588 items) tests 37012 done 69 failed | 23 in flight, oldest 721s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 4 hazardous kill call(s)
..................................F......................... [1544%]
........................................................................ [1547%]
........................................................................ [1550%]
........................................................................ [1553%]
......................................................................s. [1556%]
........................................................................ [1559%]
......................................[contention-diag] +3693s soak 42p/175t rss 15.6G pss 14.1G swap 1.7G majflt 87786 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.0G pss 12.7G, 14 descendant rss 1.3G pss 1.2G | host avail 24.2G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 1.67/0.0 io 2.94 cpu 16.67 | cgroup 14.7G/16106127360 oom_kill 0 | free scratch 329.3G/45376538i tmp 30.3G/1035656i workspace 329.3G/45376538i | repeat-01 collected 26/26 workers (60588 items) tests 37465 done 70 failed | 23 in flight, oldest 736s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 4 hazardous kill call(s)
.................................. [1562%]
..........................F............................................. [1565%]
........................................................................ [1568%]
........................................................................ [1571%]
........................................................................ [1574%]
........................................................................ [1577%]
........................................................................ [1580%]
............................................................[contention-diag] +3708s soak 37p/177t rss 15.6G pss 14.2G swap 1.7G majflt 88581 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.1G pss 12.7G, 9 descendant rss 1.3G pss 1.2G | host avail 24.1G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 1.55/0.0 io 2.62 cpu 15.85 | cgroup 14.8G/16106127360 oom_kill 0 | free scratch 329.2G/45373898i tmp 30.3G/1035653i workspace 329.2G/45373898i | scratch used 0.1G in 23989 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 37969 done 71 failed | 24 in flight, oldest 752s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 4 hazardous kill call(s)
............ [1583%]
........................................................................ [1586%]
........................................................................ [1589%]
........................................................................ [1592%]
........................................................................ [1595%]
..............................[contention-diag] +3726s soak 37p/178t rss 15.6G pss 14.0G swap 1.6G majflt 100447 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 14.1G pss 12.8G, 9 descendant rss 1.2G pss 1.0G | host avail 26.5G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.79/0.0 io 3.13 cpu 18.87 | cgroup 14.7G/16106127360 oom_kill 0 | free scratch 329.2G/45373662i tmp 30.3G/1035651i workspace 329.2G/45373662i | repeat-01 collected 26/26 workers (60588 items) tests 38328 done 71 failed | 24 in flight, oldest 769s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 4 hazardous kill call(s)
.......................................... [1598%]
........................................................................ [1601%]
........................................................................ [1604%]
........................................................................ [1607%]
........................................................................ [1610%]
.........................[contention-diag] +3741s soak 37p/183t rss 14.9G pss 13.4G swap 1.6G majflt 100860 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 9 descendant rss 1.1G pss 1.1G | host avail 26.8G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.31/0.0 io 4.05 cpu 20.65 | cgroup 14.1G/16106127360 oom_kill 0 | free scratch 329.3G/45388876i tmp 30.3G/1035650i workspace 329.3G/45388876i | repeat-01 collected 26/26 workers (60588 items) tests 38680 done 71 failed | 22 in flight, oldest 505s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 4 hazardous kill call(s)
.F............................................. [1613%]
........................................................................ [1616%]
........................................................................ [1619%]
.ss.s..............[contention-diag] +3756s soak 45p/202t rss 15.0G pss 13.5G swap 1.6G majflt 101781 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.0G, 17 descendant rss 1.3G pss 1.2G | host avail 26.4G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.06/0.0 io 7.86 cpu 19.98 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 329.5G/45433281i tmp 30.3G/1035650i workspace 329.5G/45433281i | repeat-01 collected 26/26 workers (60588 items) tests 38890 done 72 failed | 23 in flight, oldest 521s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 4 hazardous kill call(s)
..................................................... [1622%]
..................F..................................................... [1625%]
........................................................................ [1628%]
........................................................................ [1631%]
...[contention-diag] +3772s soak 41p/183t rss 15.1G pss 13.6G swap 1.6G majflt 102879 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 13 descendant rss 1.4G pss 1.3G | host avail 26.8G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.53/0.0 io 7.17 cpu 19.39 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 329.7G/45474646i tmp 30.3G/1035650i workspace 329.7G/45474646i | repeat-01 collected 26/26 workers (60588 items) tests 39164 done 73 failed | 23 in flight, oldest 536s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 4 hazardous kill call(s)
..................................................................... [1634%]
........................................................................ [1637%]
..................................................................[contention-diag] +3787s soak 38p/177t rss 14.9G pss 13.5G swap 1.6G majflt 102969 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 10 descendant rss 1.2G pss 1.1G | host avail 25.7G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.24/0.1 io 22.87 cpu 13.52 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 329.8G/45499632i tmp 30.3G/1035650i workspace 329.8G/45499632i | repeat-01 collected 26/26 workers (60588 items) tests 39357 done 73 failed | 22 in flight, oldest 551s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
...... [1640%]
........................................................................ [1643%]
........................................................................ [1646%]
........................................................................ [1649%]
...................................................[contention-diag] +3803s soak 36p/178t rss 14.9G pss 13.5G swap 1.6G majflt 103208 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 8 descendant rss 1.2G pss 1.1G | host avail 24.9G/62.7G swapfree 53.9G/64.0G oom_kill +0 | psi10 mem 0.04/0.02 io 26.06 cpu 11.87 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 330.0G/45529282i tmp 30.3G/1035650i workspace 330.0G/45529282i | repeat-01 collected 26/26 workers (60588 items) tests 39638 done 73 failed | 23 in flight, oldest 567s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
..................... [1652%]
....................F................................................... [1655%]
........................................................................ [1658%]
........................................................................ [1661%]
...............................[contention-diag] +3818s soak 35p/174t rss 14.9G pss 13.5G swap 1.6G majflt 103499 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 13.4G pss 12.1G, 7 descendant rss 1.2G pss 1.2G | host avail 25.2G/62.7G swapfree 52.7G/64.0G oom_kill +0 | psi10 mem 9.88/8.11 io 25.97 cpu 10.18 | cgroup 14.4G/16106127360 oom_kill 0 | free scratch 330.0G/45529323i tmp 30.3G/1035650i workspace 330.0G/45529323i | repeat-01 collected 26/26 workers (60588 items) tests 39915 done 74 failed | 21 in flight, oldest 582s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
......................................... [1664%]
........................................................................ [1667%]
........................................................................ [1670%]
................F......................................................[contention-diag] +3834s soak 35p/177t rss 14.4G pss 13.0G swap 2.1G majflt 103642 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 13.0G pss 11.6G, 7 descendant rss 1.2G pss 1.1G | host avail 25.5G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 3.82/2.84 io 19.15 cpu 9.05 | cgroup 13.8G/16106127360 oom_kill 0 | free scratch 330.0G/45528477i tmp 30.3G/1035650i workspace 330.0G/45528477i | scratch used 0.2G in 44499 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 40158 done 75 failed | 23 in flight, oldest 598s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
. [1673%]
........................................................................ [1676%]
..................................................[contention-diag] +3852s soak 36p/170t rss 14.0G pss 12.5G swap 2.7G majflt 105100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.1G, 8 descendant rss 1.2G pss 1.2G | host avail 26.1G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 8.12/5.08 io 17.84 cpu 8.62 | cgroup 13.3G/16106127360 oom_kill 0 | free scratch 330.0G/45526498i tmp 30.3G/1035648i workspace 330.0G/45526498i | repeat-01 collected 26/26 workers (60588 items) tests 40293 done 75 failed | 23 in flight, oldest 616s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
...................... [1679%]
........................................................................ [1682%]
........................................................................ [1685%]
...............................................................[contention-diag] +3867s soak 36p/171t rss 14.0G pss 12.5G swap 2.7G majflt 106703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.5G pss 11.1G, 8 descendant rss 1.2G pss 1.2G | host avail 31.9G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 5.6/1.02 io 5.59 cpu 21.73 | cgroup 13.3G/16106127360 oom_kill 0 | free scratch 330.0G/45526395i tmp 30.3G/1035651i workspace 330.0G/45526395i | repeat-01 collected 26/26 workers (60588 items) tests 40524 done 75 failed | 23 in flight, oldest 631s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
......... [1688%]
.................F............................................F......... [1691%]
........................................................................ [1694%]
.....................................[contention-diag] +3882s soak 41p/174t rss 14.1G pss 12.6G swap 2.6G majflt 116886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.6G pss 11.2G, 13 descendant rss 1.3G pss 1.2G | host avail 31.0G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 8.98/0.2 io 3.05 cpu 24.7 | cgroup 13.3G/16106127360 oom_kill 0 | free scratch 329.9G/45526204i tmp 30.3G/1035651i workspace 329.9G/45526204i | repeat-01 collected 26/26 workers (60588 items) tests 40712 done 77 failed | 23 in flight, oldest 646s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
..F................................ [1697%]
........................................................................ [1700%]
............F........................................................... [1703%]
...............................F.................................[contention-diag] +3898s soak 42p/187t rss 14.4G pss 12.8G swap 2.6G majflt 118173 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.7G pss 11.3G, 14 descendant rss 1.4G pss 1.3G | host avail 30.0G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 4.65/0.05 io 2.93 cpu 23.8 | cgroup 13.6G/16106127360 oom_kill 0 | free scratch 329.9G/45525108i tmp 30.3G/1035651i workspace 329.9G/45525108i | repeat-01 collected 26/26 workers (60588 items) tests 40950 done 80 failed | 23 in flight, oldest 662s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
....... [1706%]
...........F............................................................ [1709%]
...............................................................F........ [1712%]
.............................................................[contention-diag] +3913s soak 45p/198t rss 14.5G pss 12.9G swap 2.6G majflt 122594 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.8G pss 11.3G, 17 descendant rss 1.5G pss 1.3G | host avail 30.2G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 7.47/0.0 io 3.94 cpu 25.44 | cgroup 13.7G/16106127360 oom_kill 0 | free scratch 329.9G/45524065i tmp 30.3G/1035651i workspace 329.9G/45524065i | repeat-01 collected 26/26 workers (60588 items) tests 41172 done 82 failed | 23 in flight, oldest 677s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
.F......... [1715%]
.............................F.........................F................ [1718%]
..............................................[contention-diag] +3928s soak 38p/179t rss 14.5G pss 12.9G swap 2.4G majflt 145483 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.9G pss 11.5G, 10 descendant rss 1.3G pss 1.2G | host avail 29.2G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 10.25/0.0 io 1.72 cpu 23.38 | cgroup 13.8G/16106127360 oom_kill 0 | free scratch 329.9G/45524427i tmp 30.3G/1035651i workspace 329.9G/45524427i | repeat-01 collected 26/26 workers (60588 items) tests 41289 done 85 failed | 22 in flight, oldest 693s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
.......................... [1721%]
..................................F..................................... [1724%]
........................................................................ [1727%]
........................................................................ [1730%]
........................................................................ [1733%]
.......................................[contention-diag] +3944s soak 39p/180t rss 14.6G pss 13.1G swap 2.2G majflt 171840 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.2G pss 11.8G, 11 descendant rss 1.1G pss 1.1G | host avail 27.8G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 9.82/0.0 io 1.38 cpu 22.57 | cgroup 14.0G/16106127360 oom_kill 0 | free scratch 329.8G/45521100i tmp 30.3G/1035640i workspace 329.8G/45521100i | repeat-01 collected 26/26 workers (60588 items) tests 41651 done 86 failed | 23 in flight, oldest 708s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
................................. [1736%]
........................................................................ [1739%]
...........................................F............................ [1742%]
.........................F.............................................. [1745%]
..............................[contention-diag] +3959s soak 35p/169t rss 15.0G pss 13.4G swap 2.2G majflt 172591 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.4G pss 12.0G, 7 descendant rss 1.3G pss 1.2G | host avail 27.8G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 3.1/0.0 io 1.33 cpu 19.4 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 329.8G/45521096i tmp 30.3G/1035640i workspace 329.8G/45521096i | scratch used 0.3G in 60347 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 41876 done 88 failed | 22 in flight, oldest 723s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
.......................................... [1748%]
........................................................................ [1751%]
........................................................................ [1754%]
........................................................................ [1757%]
.............................................[contention-diag] +3977s soak 35p/173t rss 15.2G pss 13.6G swap 2.2G majflt 174130 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.0G, 7 descendant rss 1.4G pss 1.3G | host avail 27.1G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 3.02/0.0 io 1.62 cpu 21.46 | cgroup 14.8G/16106127360 oom_kill 0 | free scratch 329.8G/45520464i tmp 30.3G/1035640i workspace 329.8G/45520464i | repeat-01 collected 26/26 workers (60588 items) tests 42222 done 88 failed | 23 in flight, oldest 741s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 7 hazardous kill call(s)
........................... [1760%]
........................................................................ [1763%]
........................................................................ [1766%]
........................................................................ [1769%]
........................................................................ [1772%]
........................................................................ [1775%]
........................................................................ [1778%]
........................................................................ [1781%]
......[contention-diag] +3992s soak 35p/174t rss 15.2G pss 13.6G swap 2.2G majflt 175432 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.5G pss 12.1G, 7 descendant rss 1.5G pss 1.4G | host avail 28.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 2.57/0.0 io 2.12 cpu 24.22 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.8G/45517547i tmp 30.3G/1035640i workspace 329.8G/45517547i | repeat-01 collected 26/26 workers (60588 items) tests 42753 done 88 failed | 23 in flight, oldest 756s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 8 hazardous kill call(s)
.................................................................. [1784%]
........................................................................ [1787%]
........................................................................ [1790%]
........................................................................ [1793%]
..........................................[contention-diag] +4007s soak 46p/188t rss 15.3G pss 13.7G swap 2.2G majflt 176499 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.6G pss 12.1G, 18 descendant rss 1.5G pss 1.4G | host avail 28.5G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 2.16/0.0 io 2.26 cpu 23.37 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.8G/45516930i tmp 30.3G/1035640i workspace 329.8G/45516930i | repeat-01 collected 26/26 workers (60588 items) tests 43079 done 88 failed | 23 in flight, oldest 772s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 8 hazardous kill call(s)
.............................. [1796%]
........................................................................ [1799%]
........................................................................ [1802%]
........................................................................ [1805%]
........................................................................ [1808%]
..............................................................[contention-diag] +4023s soak 34p/179t rss 14.4G pss 12.8G swap 2.1G majflt 188127 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 13.8G pss 12.4G, 6 descendant rss 0.3G pss 0.2G | host avail 29.0G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 3.29/0.0 io 2.04 cpu 23.53 | cgroup 14.0G/16106127360 oom_kill 0 | free scratch 329.8G/45516756i tmp 30.3G/1035640i workspace 329.8G/45516756i | repeat-01 collected 26/26 workers (60588 items) tests 43471 done 88 failed | 23 in flight, oldest 368s gw11 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.......... [1811%]
........................................................................ [1814%]
........................................................................ [1817%]
........................................................................ [1820%]
............F........................................................... [1823%]
........................................................................ [1826%]
.......................................................[contention-diag] +4038s soak 34p/182t rss 14.6G pss 13.0G swap 2.0G majflt 209482 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 14.1G pss 12.7G, 6 descendant rss 0.2G pss 0.2G | host avail 28.8G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 4.38/0.0 io 1.41 cpu 19.72 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 329.8G/45515707i tmp 30.3G/1035639i workspace 329.8G/45515707i | repeat-01 collected 26/26 workers (60588 items) tests 43894 done 89 failed | 23 in flight, oldest 383s gw11 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................. [1829%]
........................................................................ [1832%]
........................................................................ [1835%]
........................................................................ [1838%]
........................................................................ [1841%]
........................................................................ [1844%]
.............................[contention-diag] +4054s soak 32p/171t rss 14.5G pss 13.0G swap 2.0G majflt 211526 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 14.2G pss 12.7G, 4 descendant rss 0.1G pss 0.0G | host avail 29.5G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 2.05/0.0 io 1.96 cpu 22.65 | cgroup 14.4G/16106127360 oom_kill 0 | free scratch 329.8G/45514549i tmp 30.3G/1035639i workspace 329.8G/45514549i | repeat-01 collected 26/26 workers (60588 items) tests 44293 done 89 failed | 23 in flight, oldest 312s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
........................................... [1847%]
........................................................................ [1850%]
........................................................................ [1853%]
........................................................................ [1856%]
........................................................................ [1859%]
........................................................................ [1862%]
...................[contention-diag] +4069s soak 36p/172t rss 14.5G pss 12.9G swap 2.0G majflt 212939 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 14.2G pss 12.7G, 8 descendant rss 0.1G pss 0.1G | host avail 28.3G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.45/0.0 io 2.84 cpu 21.35 | cgroup 14.5G/16106127360 oom_kill 0 | free scratch 329.8G/45513169i tmp 30.3G/1035636i workspace 329.8G/45513169i | repeat-01 collected 26/26 workers (60588 items) tests 44728 done 89 failed | 23 in flight, oldest 327s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
..................................................... [1865%]
........................................................................ [1868%]
.......................F................................................ [1871%]
..[contention-diag] +4084s soak 41p/185t rss 14.7G pss 13.1G swap 1.9G majflt 213558 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.2G pss 12.7G, 13 descendant rss 0.2G pss 0.2G | host avail 27.1G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.91/0.19 io 2.02 cpu 18.5 | cgroup 14.5G/16106127360 oom_kill 0 | free scratch 329.8G/45512216i tmp 30.3G/1035636i workspace 329.8G/45512216i | scratch used 0.5G in 97056 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 44916 done 90 failed | 23 in flight, oldest 343s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
...................................................................... [1874%]
........................................................................ [1877%]
...............................................................[contention-diag] +4102s soak 34p/178t rss 14.7G pss 13.2G swap 1.9G majflt 220215 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.2G pss 12.8G, 6 descendant rss 0.3G pss 0.2G | host avail 28.5G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.23/0.03 io 1.69 cpu 21.02 | cgroup 14.7G/16106127360 oom_kill 0 | free scratch 329.8G/45512286i tmp 30.3G/1035631i workspace 329.8G/45512286i | repeat-01 collected 26/26 workers (60588 items) tests 45130 done 90 failed | 22 in flight, oldest 360s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
......... [1880%]
........................................................................ [1883%]
........................................................................ [1886%]
........................................................................ [1889%]
.....................................................................[contention-diag] +4117s soak 34p/171t rss 14.6G pss 13.1G swap 1.9G majflt 223811 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.3G pss 12.8G, 6 descendant rss 0.1G pss 0.1G | host avail 27.6G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.5/0.0 io 2.78 cpu 24.33 | cgroup 14.6G/16106127360 oom_kill 0 | free scratch 329.8G/45511228i tmp 30.3G/1035630i workspace 329.8G/45511228i | repeat-01 collected 26/26 workers (60588 items) tests 45413 done 90 failed | 22 in flight, oldest 375s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 8 hazardous kill call(s)
... [1892%]
........................................................................ [1895%]
........................................................................ [1898%]
........................................................................ [1901%]
........................................................................ [1904%]
........................................................................ [1907%]
........................................................................ [1910%]
........................................................................ [1913%]
.....................[contention-diag] +4133s soak 34p/161t rss 14.7G pss 13.2G swap 1.9G majflt 225373 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.3G pss 12.8G, 6 descendant rss 0.1G pss 0.1G | host avail 29.4G/62.7G swapfree 51.7G/64.0G oom_kill +0 | psi10 mem 0.1/0.0 io 4.52 cpu 27.32 | cgroup 14.7G/16106127360 oom_kill 0 | free scratch 329.8G/45510030i tmp 30.3G/1035616i workspace 329.8G/45510030i | repeat-01 collected 26/26 workers (60588 items) tests 45934 done 90 failed | 22 in flight, oldest 391s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
................................................... [1916%]
........................................................................ [1919%]
........................................................................ [1922%]
..........................................................[contention-diag] +4148s soak 40p/181t rss 14.7G pss 13.1G swap 1.9G majflt 226364 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.3G pss 12.8G, 12 descendant rss 0.1G pss 0.0G | host avail 28.8G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 5.46 cpu 23.61 | cgroup 14.6G/16106127360 oom_kill 0 | free scratch 328.8G/45320051i tmp 30.3G/1035604i workspace 328.8G/45320051i | repeat-01 collected 26/26 workers (60588 items) tests 46198 done 90 failed | 21 in flight, oldest 406s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
.............. [1925%]
........................................................................ [1928%]
........................................................................ [1931%]
........................................................................ [1934%]
...............................................[contention-diag] +4164s soak 39p/181t rss 14.8G pss 13.2G swap 1.8G majflt 233115 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.3G pss 12.9G, 11 descendant rss 0.2G pss 0.0G | host avail 28.6G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.22/0.22 io 8.32 cpu 20.25 | cgroup 14.7G/16106127360 oom_kill 0 | free scratch 329.2G/45412779i tmp 30.3G/1035602i workspace 329.2G/45412779i | repeat-01 collected 26/26 workers (60588 items) tests 46479 done 90 failed | 22 in flight, oldest 422s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
......................... [1937%]
........................................................................ [1940%]
........................................................................ [1943%]
..................................................F...............[contention-diag] +4179s soak 36p/181t rss 14.9G pss 13.3G swap 1.7G majflt 248009 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.5G pss 13.0G, 8 descendant rss 0.1G pss 0.1G | host avail 28.3G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.15/0.15 io 4.67 cpu 20.16 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.2G/45412743i tmp 30.3G/1035595i workspace 329.2G/45412743i | repeat-01 collected 26/26 workers (60588 items) tests 46717 done 91 failed | 20 in flight, oldest 437s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
...... [1946%]
........................................................................ [1949%]
........................................................................ [1952%]
......................................................................[contention-diag] +4194s soak 34p/173t rss 14.9G pss 13.4G swap 1.6G majflt 258442 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.6G pss 13.1G, 6 descendant rss 0.0G pss 0.0G | host avail 28.6G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.47/0.14 io 4.39 cpu 22.37 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.2G/45412211i tmp 30.3G/1035595i workspace 329.2G/45412211i | repeat-01 collected 26/26 workers (60588 items) tests 46940 done 91 failed | 20 in flight, oldest 452s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
.. [1955%]
........................................................................ [1958%]
........................................................................ [1961%]
........................................................................ [1964%]
............................................................[contention-diag] +4210s soak 34p/179t rss 15.0G pss 13.4G swap 1.6G majflt 258643 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.6G pss 13.1G, 6 descendant rss 0.1G pss 0.1G | host avail 27.7G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.16/0.02 io 3.46 cpu 18.28 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.2G/45411212i tmp 30.3G/1035597i workspace 329.2G/45411212i | scratch used 0.6G in 107563 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 47138 done 91 failed | 20 in flight, oldest 468s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
............ [1967%]
........................................................................ [1970%]
........................................................................ [1973%]
........................................................................ [1976%]
...................................................[contention-diag] +4227s soak 33p/174t rss 15.0G pss 13.4G swap 1.6G majflt 259360 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.6G pss 13.1G, 5 descendant rss 0.1G pss 0.0G | host avail 28.7G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.34/0.0 io 2.29 cpu 19.88 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.2G/45410037i tmp 30.3G/1035597i workspace 329.2G/45410037i | repeat-01 collected 26/26 workers (60588 items) tests 47485 done 91 failed | 20 in flight, oldest 485s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
..................... [1979%]
........................................................................ [1982%]
........................................................................ [1985%]
.................................................F...................... [1988%]
...............................................[contention-diag] +4243s soak 37p/171t rss 15.2G pss 13.6G swap 1.7G majflt 260444 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.6G pss 13.1G, 9 descendant rss 0.4G pss 0.3G | host avail 28.3G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.76/0.0 io 2.21 cpu 20.87 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.2G/45408737i tmp 30.3G/1035597i workspace 329.2G/45408737i | repeat-01 collected 26/26 workers (60588 items) tests 47766 done 92 failed | 20 in flight, oldest 501s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
......................... [1991%]
........................................................................ [1994%]
........................................................................ [1997%]
........................................................................ [2000%]
.................................................[contention-diag] +4258s soak 44p/177t rss 15.1G pss 13.4G swap 1.7G majflt 260679 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.5G pss 13.0G, 16 descendant rss 0.3G pss 0.2G | host avail 27.1G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.65/0.04 io 3.0 cpu 23.09 | cgroup 14.9G/16106127360 oom_kill 0 | free scratch 329.2G/45407229i tmp 30.3G/1035597i workspace 329.2G/45407229i | repeat-01 collected 26/26 workers (60588 items) tests 48070 done 92 failed | 20 in flight, oldest 516s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
....................... [2003%]
........................................................................ [2006%]
........................................................................ [2009%]
........................................................................ [2012%]
........................................................................ [2015%]
...........................................................[contention-diag] +4273s soak 38p/171t rss 14.9G pss 13.3G swap 1.7G majflt 261068 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 14.6G pss 13.1G, 10 descendant rss 0.1G pss 0.0G | host avail 28.5G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.7/0.0 io 1.75 cpu 24.36 | cgroup 14.8G/16106127360 oom_kill 0 | free scratch 329.2G/45406910i tmp 30.3G/1035597i workspace 329.2G/45406910i | repeat-01 collected 26/26 workers (60588 items) tests 48407 done 92 failed | 20 in flight, oldest 531s gw3 tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command | 9 hazardous kill call(s)
............. [2018%]
........................................................................ [2021%]
........................................................................ [2024%]
........................................................................ [2027%]
........................................................................ [2030%]
........................................................................ [2033%]
...............................[contention-diag] +4289s soak 36p/172t rss 14.5G pss 12.9G swap 1.6G majflt 271041 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.9G pss 12.4G, 8 descendant rss 0.3G pss 0.2G | host avail 28.7G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 4.22/0.0 io 1.18 cpu 23.23 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 329.2G/45407749i tmp 30.3G/1035597i workspace 329.2G/45407749i | repeat-01 collected 26/26 workers (60588 items) tests 48841 done 92 failed | 18 in flight, oldest 256s gw8 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
......................................... [2036%]
........................................................................ [2039%]
........................................................................ [2042%]
........................................................................ [2045%]
........................................................................ [2048%]
........................................................................ [2051%]
........................................................................ [2054%]
........................................................................ [2057%]
...................................................................[contention-diag] +4304s soak 36p/164t rss 14.4G pss 12.8G swap 1.6G majflt 271494 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.8G pss 12.3G, 8 descendant rss 0.3G pss 0.2G | host avail 28.0G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.98/0.0 io 0.54 cpu 19.87 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 329.2G/45405550i tmp 30.3G/1035597i workspace 329.2G/45405550i | repeat-01 collected 26/26 workers (60588 items) tests 49451 done 92 failed | 18 in flight, oldest 271s gw8 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..... [2060%]
........................................................................ [2063%]
........................................................................ [2066%]
....[contention-diag] +4320s soak 39p/183t rss 14.8G pss 13.1G swap 1.6G majflt 272245 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.8G pss 12.3G, 11 descendant rss 0.6G pss 0.5G | host avail 27.5G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 2.61/0.3 io 0.64 cpu 17.75 | cgroup 14.6G/16106127360 oom_kill 0 | free scratch 329.2G/45405466i tmp 30.3G/1035596i workspace 329.2G/45405466i | repeat-01 collected 26/26 workers (60588 items) tests 49609 done 92 failed | 18 in flight, oldest 286s gw8 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................................................... [2069%]
........................................................................ [2072%]
........[contention-diag] +4335s soak 36p/182t rss 14.8G pss 13.2G swap 1.6G majflt 272501 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.8G pss 12.3G, 8 descendant rss 0.6G pss 0.6G | host avail 27.6G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.98/0.15 io 0.55 cpu 19.61 | cgroup 15.0G/16106127360 oom_kill 0 | free scratch 329.2G/45405066i tmp 30.3G/1035597i workspace 329.2G/45405066i | scratch used 0.6G in 116057 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 49736 done 92 failed | 18 in flight, oldest 302s gw8 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
......................................F......................... [2075%]
........................................................................ [2078%]
.................................................[contention-diag] +4352s soak 38p/173t rss 14.3G pss 12.7G swap 1.7G majflt 272742 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.2G, 10 descendant rss 0.3G pss 0.2G | host avail 27.8G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 1.54/0.13 io 2.22 cpu 21.49 | cgroup 14.8G/16106127360 oom_kill 0 | free scratch 328.8G/45403926i tmp 30.3G/1035597i workspace 328.8G/45403926i | repeat-01 collected 26/26 workers (60588 items) tests 49939 done 93 failed | 18 in flight, oldest 319s gw8 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
....................... [2081%]
........................................................................ [2084%]
........................................................................ [2087%]
........................................................................ [2090%]
.............[contention-diag] +4368s soak 39p/172t rss 14.4G pss 12.8G swap 1.7G majflt 272946 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.2G, 11 descendant rss 0.4G pss 0.3G | host avail 28.9G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.31/0.02 io 3.78 cpu 19.73 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 328.6G/45402856i tmp 30.3G/1035597i workspace 328.6G/45402856i | repeat-01 collected 26/26 workers (60588 items) tests 50196 done 93 failed | 18 in flight, oldest 335s gw8 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................................................... [2093%]
........................................................................ [2096%]
........................................................................ [2099%]
........................................................................ [2102%]
.................................................................[contention-diag] +4383s soak 35p/162t rss 14.4G pss 12.8G swap 1.7G majflt 273228 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.2G, 7 descendant rss 0.3G pss 0.3G | host avail 27.7G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.06/0.0 io 1.38 cpu 20.8 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 328.0G/45395078i tmp 30.3G/1035596i workspace 328.0G/45395078i | repeat-01 collected 26/26 workers (60588 items) tests 50529 done 93 failed | 18 in flight, oldest 350s gw8 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
....... [2105%]
........................................................................ [2108%]
........................................................................ [2111%]
........................................................................ [2114%]
........................................................................ [2117%]
........................................................................ [2120%]
..................................................................[contention-diag] +4398s soak 35p/166t rss 14.2G pss 12.6G swap 1.7G majflt 273916 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.2G, 7 descendant rss 0.1G pss 0.1G | host avail 26.9G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.19/0.0 io 1.87 cpu 19.66 | cgroup 14.0G/16106127360 oom_kill 0 | free scratch 328.0G/45393700i tmp 30.3G/1035596i workspace 328.0G/45393700i | repeat-01 collected 26/26 workers (60588 items) tests 50966 done 93 failed | 18 in flight, oldest 232s gw6 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 9 hazardous kill call(s)
...... [2123%]
........................................................................ [2126%]
........................................................................ [2129%]
........................................................................ [2132%]
........................................................................ [2135%]
........................................................................ [2138%]
........................................................................ [2141%]
........................................................................ [2144%]
........................................................................ [2147%]
.[contention-diag] +4414s soak 44p/180t rss 14.3G pss 12.7G swap 1.7G majflt 274118 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.2G, 16 descendant rss 0.2G pss 0.1G | host avail 29.2G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.0 io 4.01 cpu 24.78 | cgroup 14.0G/16106127360 oom_kill 0 | free scratch 328.0G/45392257i tmp 30.3G/1035596i workspace 328.0G/45392257i | repeat-01 collected 26/26 workers (60588 items) tests 51528 done 93 failed | 18 in flight, oldest 247s gw6 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 9 hazardous kill call(s)
....................................................................... [2150%]
........................................................................ [2153%]
........................................................................ [2156%]
........................................................................ [2159%]
........................................................................ [2162%]
........................................................................ [2165%]
.................................................[contention-diag] +4429s soak 41p/194t rss 14.4G pss 12.7G swap 1.7G majflt 274352 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.2G, 13 descendant rss 0.3G pss 0.2G | host avail 29.2G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.53 cpu 26.43 | cgroup 14.1G/16106127360 oom_kill 0 | free scratch 328.0G/45391562i tmp 30.3G/1035596i workspace 328.0G/45391562i | repeat-01 collected 26/26 workers (60588 items) tests 52022 done 93 failed | 16 in flight, oldest 263s gw6 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 9 hazardous kill call(s)
...F................... [2168%]
........................................................................ [2171%]
..........................................[contention-diag] +4445s soak 47p/206t rss 14.6G pss 12.9G swap 1.7G majflt 274516 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.2G, 19 descendant rss 0.5G pss 0.4G | host avail 27.3G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.57 cpu 26.24 | cgroup 14.4G/16106127360 oom_kill 0 | free scratch 328.0G/45392027i tmp 30.3G/1035596i workspace 328.0G/45392027i | repeat-01 collected 26/26 workers (60588 items) tests 52165 done 94 failed | 16 in flight, oldest 278s gw6 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 9 hazardous kill call(s)
.............................. [2174%]
........................................................................ [2177%]
........................................................................ [2180%]
........................................................................ [2183%]
...[contention-diag] +4460s soak 38p/169t rss 14.4G pss 12.8G swap 1.7G majflt 274598 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 13.7G pss 12.2G, 10 descendant rss 0.3G pss 0.2G | host avail 27.8G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.22 cpu 22.29 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 328.0G/45391645i tmp 30.3G/1035596i workspace 328.0G/45391645i | scratch used 0.3G in 49281 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 52399 done 94 failed | 16 in flight, oldest 293s gw6 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 9 hazardous kill call(s)
..................................................................... [2186%]
........................................................................ [2189%]
........................................................................ [2192%]
........................................................................ [2195%]
........................................................................ [2198%]
........................................................................ [2201%]
........................................................................ [2204%]
........................................................................ [2207%]
........................................................................ [2210%]
........................................................................ [2213%]
......[contention-diag] +4478s soak 38p/159t rss 14.3G pss 12.7G swap 1.7G majflt 275125 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.7G pss 12.2G, 10 descendant rss 0.2G pss 0.1G | host avail 29.3G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.54 cpu 24.18 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 328.0G/45389962i tmp 30.3G/1035596i workspace 328.0G/45389962i | repeat-01 collected 26/26 workers (60588 items) tests 53141 done 94 failed | 15 in flight, oldest 311s gw6 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 9 hazardous kill call(s)
.................................................................. [2216%]
........................................................................ [2219%]
........................................................................ [2222%]
........................................................................ [2225%]
..........................................................s............. [2228%]
........................................................................ [2231%]
........................................................................ [2234%]
........................................................................ [2237%]
........................................................................ [2240%]
...................................................[contention-diag] +4493s soak 38p/161t rss 14.2G pss 12.6G swap 1.6G majflt 275827 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.7G pss 12.2G, 10 descendant rss 0.1G pss 0.1G | host avail 30.2G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.44 cpu 24.25 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 328.0G/45387927i tmp 30.3G/1035596i workspace 328.0G/45387927i | repeat-01 collected 26/26 workers (60588 items) tests 53834 done 94 failed | 15 in flight, oldest 113s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 9 hazardous kill call(s)
..................... [2243%]
......................................s................................. [2246%]
........................................................................ [2249%]
.....s.................................................................. [2252%]
........................................................................ [2255%]
........................................................................ [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
........................................................................ [2267%]
...........................[contention-diag] +4508s soak 35p/155t rss 14.3G pss 12.7G swap 1.6G majflt 276472 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.7G pss 12.2G, 7 descendant rss 0.2G pss 0.2G | host avail 28.9G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.15 cpu 22.49 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 328.0G/45386028i tmp 30.3G/1035596i workspace 328.0G/45386028i | repeat-01 collected 26/26 workers (60588 items) tests 54458 done 94 failed | 15 in flight, oldest 129s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 9 hazardous kill call(s)
............................................. [2270%]
........................................................................ [2273%]
........................................................................ [2276%]
........................................................................ [2279%]
........................................................[contention-diag] +4524s soak 37p/160t rss 14.4G pss 12.8G swap 1.6G majflt 276937 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.2G, 9 descendant rss 0.3G pss 0.2G | host avail 29.3G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.0 cpu 24.12 | cgroup 14.4G/16106127360 oom_kill 0 | free scratch 328.0G/45384868i tmp 30.3G/1035593i workspace 328.0G/45384868i | repeat-01 collected 26/26 workers (60588 items) tests 54755 done 94 failed | 13 in flight, oldest 28s gw7 tests/test_proc_observer_isolation.py::test_constructed_ace_app_does_not_poison_a_later_test | 9 hazardous kill call(s)
................ [2282%]
........................................................................ [2285%]
........................................................................ [2288%]
........................................................................ [2291%]
........................................................................ [2294%]
................s....................................................... [2297%]
........................................................................ [2300%]
........................................................................ [2303%]
........................................................................ [2306%]
......[contention-diag] +4539s soak 34p/157t rss 14.3G pss 12.7G swap 1.6G majflt 277179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.2G, 6 descendant rss 0.1G pss 0.1G | host avail 30.0G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.57 cpu 23.34 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 328.0G/45384058i tmp 30.3G/1035592i workspace 328.0G/45384058i | repeat-01 collected 26/26 workers (60588 items) tests 55345 done 94 failed | 12 in flight, oldest 16s gw18 tests/tool/test_inline_escalation.py::test_slow_command_escalates_and_wait_returns_exit | 9 hazardous kill call(s)
.................................................................. [2309%]
........................................................................ [2312%]
........................................................................ [2315%]
........................................................................ [2318%]
........................................................................ [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
........................................................................ [2330%]
........................................................................ [2333%]
................................................................[contention-diag] +4554s soak 35p/163t rss 14.4G pss 12.8G swap 1.6G majflt 277329 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.2G, 7 descendant rss 0.2G pss 0.2G | host avail 29.9G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 4.78 cpu 24.45 | cgroup 14.4G/16106127360 oom_kill 0 | free scratch 328.0G/45382346i tmp 30.3G/1035589i workspace 328.0G/45382346i | repeat-01 collected 26/26 workers (60588 items) tests 56067 done 94 failed | 14 in flight, oldest 24s gw23 tests/tool/test_nested_stage_recording.py::test_child_pytest_of_a_stageless_run_records_no_stage_rows | 10 hazardous kill call(s)
........ [2336%]
........................................................................ [2339%]
........................................................................ [2342%]
........................................................................ [2345%]
........................................................................ [2348%]
........................................................................ [2351%]
........................................................................ [2354%]
........................................................................ [2357%]
........................................................................ [2360%]
........................................................................ [2363%]
.............................................[contention-diag] +4570s soak 38p/159t rss 14.5G pss 12.9G swap 1.6G majflt 277392 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.2G, 10 descendant rss 0.4G pss 0.3G | host avail 29.6G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 5.69 cpu 21.24 | cgroup 14.4G/16106127360 oom_kill 0 | free scratch 328.0G/45380289i tmp 30.3G/1035588i workspace 328.0G/45380289i | repeat-01 collected 26/26 workers (60588 items) tests 56748 done 94 failed | 14 in flight, oldest 13s gw23 tests/tool/test_nested_stage_recording.py::test_fixtures_that_run_run_silent_leave_the_enclosing_run_alone | 10 hazardous kill call(s)
........................... [2366%]
........................................................................ [2369%]
........................................................................ [2372%]
........................................................................ [2375%]
........................................................................ [2378%]
........................................................................ [2381%]
........................................................................ [2384%]
........................................................................ [2387%]
........................................................................ [2390%]
........................................................................ [2393%]
........................................................................ [2396%]
........................[contention-diag] +4585s soak 38p/156t rss 14.4G pss 12.8G swap 1.6G majflt 277521 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.2G, 10 descendant rss 0.3G pss 0.2G | host avail 29.7G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.43 cpu 22.52 | cgroup 14.4G/16106127360 oom_kill 0 | free scratch 327.9G/45378007i tmp 30.3G/1035583i workspace 327.9G/45378007i | scratch used 0.7G in 123882 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 57379 done 94 failed | 13 in flight, oldest 29s gw23 tests/tool/test_nested_stage_recording.py::test_fixtures_that_run_run_silent_leave_the_enclosing_run_alone | 10 hazardous kill call(s)
................................................ [2399%]
........................................................................ [2401%]
........................................................................ [2404%]
........................................................................ [2407%]
........................................................................ [2410%]
........................................................................ [2413%]
........................................................................ [2416%]
........................................................................ [2419%]
............................................................[contention-diag] +4602s soak 37p/163t rss 14.3G pss 12.7G swap 1.6G majflt 277952 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.2G, 9 descendant rss 0.1G pss 0.0G | host avail 29.8G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 4.74 cpu 21.07 | cgroup 14.3G/16106127360 oom_kill 0 | free scratch 327.9G/45378149i tmp 30.3G/1035583i workspace 327.9G/45378149i | repeat-01 collected 26/26 workers (60588 items) tests 58156 done 94 failed | 11 in flight, oldest 34s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
............ [2422%]
........................................................................ [2425%]
........................................................................ [2428%]
........................................................................ [2431%]
........................................................................ [2434%]
...................................................[contention-diag] +4618s soak 39p/162t rss 14.5G pss 12.8G swap 1.6G majflt 278034 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.2G, 11 descendant rss 0.3G pss 0.2G | host avail 29.9G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.21/0.21 io 4.05 cpu 22.14 | cgroup 14.4G/16106127360 oom_kill 0 | free scratch 327.9G/45379512i tmp 30.3G/1035583i workspace 327.9G/45379511i | repeat-01 collected 26/26 workers (60588 items) tests 58478 done 94 failed | 8 in flight, oldest 49s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
..................... [2437%]
........................................................................ [2440%]
........................................................................ [2443%]
........................................................................ [2446%]
........................................................................ [2449%]
........................................................................ [2452%]
.......................................................................[contention-diag] +4633s soak 39p/176t rss 14.5G pss 12.9G swap 1.6G majflt 278107 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.8G pss 12.2G, 11 descendant rss 0.3G pss 0.2G | host avail 27.9G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 3.83 cpu 21.45 | cgroup 14.2G/16106127360 oom_kill 0 | free scratch 327.9G/45379078i tmp 30.3G/1035583i workspace 327.9G/45379078i | repeat-01 collected 26/26 workers (60588 items) tests 58965 done 94 failed | 7 in flight, oldest 64s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
. [2455%]
........................................................................ [2458%]
........................................................................ [2461%]
........................................................................ [2464%]
........................................................................ [2467%]
........................................................................ [2470%]
.........................................................[contention-diag] +4649s soak 35p/151t rss 14.2G pss 12.6G swap 1.6G majflt 278244 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.7G pss 12.2G, 7 descendant rss 0.1G pss 0.0G | host avail 26.9G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.28 cpu 21.99 | cgroup 13.9G/16106127360 oom_kill 0 | free scratch 327.9G/45380033i tmp 30.3G/1035583i workspace 327.9G/45380033i | repeat-01 collected 26/26 workers (60588 items) tests 59382 done 94 failed | 5 in flight, oldest 80s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
............... [2473%]
........................................................................ [2476%]
........................................................................ [2479%]
........................................................................ [2482%]
........................................................................ [2485%]
........................................................................ [2488%]
........................................................................ [2491%]
...................................[contention-diag] +4664s soak 32p/147t rss 14.2G pss 12.6G swap 1.6G majflt 278339 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.7G pss 12.2G, 4 descendant rss 0.0G pss 0.0G | host avail 27.8G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.01 cpu 22.28 | cgroup 13.9G/16106127360 oom_kill 0 | free scratch 327.9G/45380013i tmp 30.3G/1035583i workspace 327.9G/45380013i | repeat-01 collected 26/26 workers (60588 items) tests 59804 done 94 failed | 3 in flight, oldest 0s gw8 tests/test_notification_modal_sections.py::test_styled_label_without_chip_matches_chipless_render | 10 hazardous kill call(s)
..................................... [2494%]
........................................................................ [2497%]
........................................................................ [2500%]
........................................................................ [2503%]
........................................................................ [2506%]
........................................................................ [2509%]
........................................................................ [2512%]
...............................[contention-diag] +4680s soak 34p/152t rss 14.2G pss 12.6G swap 1.6G majflt 278900 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.7G pss 12.2G, 6 descendant rss 0.0G pss 0.0G | host avail 27.7G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.73 cpu 8.47 | cgroup 13.9G/16106127360 oom_kill 0 | free scratch 327.9G/45379235i tmp 30.3G/1035583i workspace 327.9G/45379235i | repeat-01 collected 26/26 workers (60588 items) tests 60364 done 94 failed | 2 in flight, oldest 0s gw4 tests/tool/test_keep_going.py::test_continuation_never_returns_zero_after_a_failed_stage[True-outcomes4] | 10 hazardous kill call(s)
......................................... [2515%]
................ssss.................................................... [2518%]
........................................................................ [2521%]
....................................                                     [100%][contention-diag] +4695s soak 32p/146t rss 14.2G pss 12.6G swap 1.6G majflt 278913 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 13.7G pss 12.2G, 4 descendant rss 0.0G pss 0.0G | host avail 28.1G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 4.28 cpu 2.19 | cgroup 13.9G/16106127360 oom_kill 0 | free scratch 327.9G/45380250i tmp 30.3G/1035583i workspace 327.9G/45380249i | repeat-01 collected 26/26 workers (60588 items) tests 60577 done 94 failed | 10 hazardous kill call(s)


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________ test_image_modal_resize_rerenders_with_new_viewport ______________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw8/test_image_modal_resize_rerend0')

    async def test_image_modal_resize_rerenders_with_new_viewport(
        tmp_path: Path,
    ) -> None:
        image = tmp_path / "sample.png"
        _write_image(image)
        app = _ImagePreviewModalTestApp(_image_payload(image))
    
        async with app.run_test(size=(100, 30)) as pilot:
            modal = app.screen_stack[-1]
            assert isinstance(modal, ImagePreviewPanelModal)
            await wait_for(
                pilot,
                lambda: isinstance(
                    modal._image_renderable,  # noqa: SLF001
                    CellImageRenderable,
                ),
            )
            await pilot.pause()
            first_size = modal._image_requested_size  # noqa: SLF001
            assert first_size is not None
    
            await pilot.resize_terminal(140, 40)
            await wait_for(
                pilot,
                lambda: modal._last_geometry_screen == (140, 40),  # noqa: SLF001
            )
    
            def _second_render_landed() -> bool:
                requested = modal._image_requested_size  # noqa: SLF001
                renderable = modal._image_renderable  # noqa: SLF001
                return (
                    requested is not None
                    and requested != first_size
                    and isinstance(renderable, CellImageRenderable)
                    and (renderable.columns, renderable.rows) == requested
                )
    
>           await wait_for(pilot, _second_render_landed)

tests/ace/tui/modals/test_preview_panel_image_modal.py:182: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/wait.py:88: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function test_image_modal_resize_rerenders_with_new_viewport.<locals>._second_render_landed at 0x7fa97bf480f0>

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
E               AssertionError: wait_for(test_image_modal_resize_rerenders_with_new_viewport.<locals>._second_render_landed) timed out after 5.0s waiting for it to return True

src/sase/ace/testing/wait.py:54: AssertionError
______ test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke _______
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6cea24da90>

    async def test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A reopen during grammar loading refreshes when the shared worker lands."""
        from unittest.mock import patch as mock_patch
    
        from sase.ace.testing import AcePage, make_patch
        from sase.ace.tui import AceApp
        from sase.ace.tui.command_line import grammar
        from sase.ace.tui.command_line.screen import CommandLineScreen
        from sase.ace.tui.command_line.screen_constants import (
            COMMAND_LINE_IDLE_HINT,
            COMMAND_LINE_INDEXING_HINT,
        )
        from textual.widgets import Static
    
        release_grammar = threading.Event()
    
        def _wait_for_grammar_release() -> object:
            assert release_grammar.wait(timeout=5.0)
            return object()
    
        monkeypatch.setattr(
            grammar, "_load_command_line_grammar_sync", _wait_for_grammar_release
        )
        with (
            mock_patch.object(AceApp, "_load_agents"),
            mock_patch.object(AceApp, "_load_axe_status"),
        ):
            async with AcePage(query="test_feature", patches=[make_patch()]) as page:
                try:
                    page.app.action_open_command_line()
                    await page.expect_modal("CommandLineScreen")
                    first = page.app.screen
                    assert isinstance(first, CommandLineScreen)
                    await page.wait_for(
                        lambda _state: page.app._command_line_grammar_loading is True
                    )
    
                    # The escape press races a blocked grammar worker; 1s is too
                    # tight under parallel-check load (observed TimeoutError on a
                    # loaded gate while isolated reruns pass in ~2s).
                    await asyncio.wait_for(page.press("escape"), timeout=5.0)
                    await page.expect_no_modal()
                    assert first.is_attached is False
    
                    page.app.action_open_command_line()
                    await page.expect_modal("CommandLineScreen")
                    reopened = page.app.screen
                    assert isinstance(reopened, CommandLineScreen)
                    hint = reopened.query_one("#command-line-hint-row", Static)
                    reopened._show_indexing(has_text=True)
>                   assert str(hint.render()) == COMMAND_LINE_INDEXING_HINT
E                   AssertionError: assert 'type to sear...mmand Palette' == 'indexing commands…'
E                     
E                     - indexing commands…
E                     + type to search · ⇥ complete · ; Command Palette

tests/ace/tui/command_line/test_panel_shell_pilot.py:230: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.ace.tui.command_line.grammar:grammar.py:154 command-line grammar failed to load: assert False
 +  where False = wait(timeout=5.0)
 +    where wait = <threading.Event at 0x7f6ce8f7cad0: unset>.wait
_______________ test_mounted_stuck_loading_card_clears_on_pulse ________________
[gw20] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0b24a72350>

    async def test_mounted_stuck_loading_card_clears_on_pulse(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Leaving an Archive run for the pulse never sticks the loading card."""
        from tests.ace.tui.visual._ace_agents_png_snapshot_helpers import page_svg_text
    
        patch_startup_loaders(monkeypatch, agents=[_inbox_agent()])
>       async with AcePage(initial_tab="agents", size=(160, 40)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_agent_archive_remaining_proof.py:230: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <sase.ace.testing.ace_page.AcePage object at 0x7f0b133d3570>

    async def __aenter__(self) -> "AcePage":
        stack = AsyncExitStack()
        await stack.__aenter__()
        self._stack = stack
        try:
            stack.enter_context(
                patch(
                    "sase.ace.patch.find_all_patches",
                    return_value=self._patches,
                )
            )
            stack.enter_context(
                patch(
                    "sase.ace.patch.find_all_patches_cached",
                    return_value=self._patches,
                )
            )
            stack.enter_context(
                patch(
                    "sase.ace.patch.find_all_patches_cached",
                    return_value=self._patches,
                )
            )
            if self._startup_policy == "fast":
                _install_fast_startup_overrides(stack)
    
            self._app = AceApp(
                query=self._query,
                model_tier_override=self._model_tier_override,
                refresh_interval=0,
                initial_tab=self._initial_tab,
            )
            if self._startup_policy == "fast":
                self._app.animation_level = "none"
                self._stylesheet_seed = seed_fast_stylesheet(self._app)
            self._pilot = await stack.enter_async_context(
                self._app.run_test(
                    size=self._size,
                    notifications=self._notifications,
                )
            )
            if self._wait_for_startup_state:
                deadline = asyncio.get_running_loop().time() + 15.0
                paused = False
                while not self._app._mount_state_loads_done:
                    if asyncio.get_running_loop().time() >= deadline:
>                       raise AssertionError(
                            "AcePage startup state did not load within 15 seconds"
                        )
E                       AssertionError: AcePage startup state did not load within 15 seconds

src/sase/ace/testing/ace_page.py:320: AssertionError
_________________ test_clicking_a_banner_toggles_it_like_enter _________________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6cf38273f0>

    async def test_clicking_a_banner_toggles_it_like_enter(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch, agents=[_inbox_agent()])
>       async with AcePage(initial_tab="agents", size=(160, 40)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_agent_archive_column_app.py:265: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <sase.ace.testing.ace_page.AcePage object at 0x7f6cdb0e6f10>

    async def __aenter__(self) -> "AcePage":
        stack = AsyncExitStack()
        await stack.__aenter__()
        self._stack = stack
        try:
            stack.enter_context(
                patch(
                    "sase.ace.patch.find_all_patches",
                    return_value=self._patches,
                )
            )
            stack.enter_context(
                patch(
                    "sase.ace.patch.find_all_patches_cached",
                    return_value=self._patches,
                )
            )
            stack.enter_context(
                patch(
                    "sase.ace.patch.find_all_patches_cached",
                    return_value=self._patches,
                )
            )
            if self._startup_policy == "fast":
                _install_fast_startup_overrides(stack)
    
            self._app = AceApp(
                query=self._query,
                model_tier_override=self._model_tier_override,
                refresh_interval=0,
                initial_tab=self._initial_tab,
            )
            if self._startup_policy == "fast":
                self._app.animation_level = "none"
                self._stylesheet_seed = seed_fast_stylesheet(self._app)
            self._pilot = await stack.enter_async_context(
                self._app.run_test(
                    size=self._size,
                    notifications=self._notifications,
                )
            )
            if self._wait_for_startup_state:
                deadline = asyncio.get_running_loop().time() + 15.0
                paused = False
                while not self._app._mount_state_loads_done:
                    if asyncio.get_running_loop().time() >= deadline:
>                       raise AssertionError(
                            "AcePage startup state did not load within 15 seconds"
                        )
E                       AssertionError: AcePage startup state did not load within 15 seconds

src/sase/ace/testing/ace_page.py:320: AssertionError
_________ test_cleanup_dismiss_partial_clan_keeps_panel_and_container __________
[gw11] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f22a6bae580>

    async def test_cleanup_dismiss_partial_clan_keeps_panel_and_container(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Dismissing one of two clan members keeps ``@epic`` and its container."""
        done = _clan_member("alpha.done", "alpha-done")
        running = _clan_member("alpha.running", "alpha-running", status="RUNNING", pid=103)
        home = _home_agent()
        patch_startup_loaders(monkeypatch, agents=[done, running, home])
    
        async with AcePage(
            query='"demo"',
            patches=patches(),
            initial_tab="agents",
        ) as page:
>           await wait_for_startup(page)

tests/ace/tui/test_agent_cleanup_panel_clan_sticky_e2e.py:198: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/_ace_png_snapshot_startup.py:530: in wait_for_startup
    await page.wait_for(
src/sase/ace/testing/ace_page.py:558: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f22b4b5d900>

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
E               AssertionError: wait_for() timed out after 15.0s — predicate never returned True

src/sase/ace/testing/wait.py:54: AssertionError
_______ test_real_ace_page_query_clear_retry_records_the_live_transition _______
[gw19] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f52418aba80>

    async def test_real_ace_page_query_clear_retry_records_the_live_transition(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Exercise the ladder against the real app, not only a navigation harness."""
        now = datetime(2026, 9, 10, 12, 0, 0)
        agents = [
            Agent(
                agent_type=AgentType.RUNNING,
                cl_name="visible",
                project_file="/tmp/project/project.sase",
                status="RUNNING",
                start_time=now,
            ),
            Agent(
                agent_type=AgentType.RUNNING,
                cl_name="hidden",
                project_file="/tmp/project/project.sase",
                status="FAILED",
                start_time=now,
            ),
        ]
        patch_startup_loaders(monkeypatch, agents=agents)
    
>       async with AcePage(initial_tab="agents") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_node_jump_ladder.py:191: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <sase.ace.testing.ace_page.AcePage object at 0x7f52619ec3c0>

    async def __aenter__(self) -> "AcePage":
        stack = AsyncExitStack()
        await stack.__aenter__()
        self._stack = stack
        try:
            stack.enter_context(
                patch(
                    "sase.ace.patch.find_all_patches",
                    return_value=self._patches,
                )
            )
            stack.enter_context(
                patch(
                    "sase.ace.patch.find_all_patches_cached",
                    return_value=self._patches,
                )
            )
            stack.enter_context(
                patch(
                    "sase.ace.patch.find_all_patches_cached",
                    return_value=self._patches,
                )
            )
            if self._startup_policy == "fast":
                _install_fast_startup_overrides(stack)
    
            self._app = AceApp(
                query=self._query,
                model_tier_override=self._model_tier_override,
                refresh_interval=0,
                initial_tab=self._initial_tab,
            )
            if self._startup_policy == "fast":
                self._app.animation_level = "none"
                self._stylesheet_seed = seed_fast_stylesheet(self._app)
            self._pilot = await stack.enter_async_context(
                self._app.run_test(
                    size=self._size,
                    notifications=self._notifications,
                )
            )
            if self._wait_for_startup_state:
                deadline = asyncio.get_running_loop().time() + 15.0
                paused = False
                while not self._app._mount_state_loads_done:
                    if asyncio.get_running_loop().time() >= deadline:
>                       raise AssertionError(
                            "AcePage startup state did not load within 15 seconds"
                        )
E                       AssertionError: AcePage startup state did not load within 15 seconds

src/sase/ace/testing/ace_page.py:320: AssertionError
___________________ test_runner_collects_synthetic_provider ____________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

runner_home = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw1/test_runner_collects_synthetic0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f4c5dfbb850>

    def test_runner_collects_synthetic_provider(
        runner_home: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        monkeypatch.delenv(SYNTHETIC_MODE_ENV, raising=False)
        results = _run_admitted_refresh(
            {
                "batch_deadline_seconds": 8,
                "provider_deadline_seconds": 6,
                "max_concurrent": 3,
                "plugin_specs": {"synth": SYNTHETIC_PLUGIN_SPEC},
                "providers": [
                    {
                        "provider": "synth",
                        "context_id": "default",
                        "account_generation": 1,
                        "lease_id": "lease-synth",
                    }
                ],
            }
        )
        assert results[0]["provider"] == "synth"
>       assert results[0]["outcome"] == "ok"
E       AssertionError: assert 'error' == 'ok'
E         
E         - ok
E         + error

tests/llm_provider/test_usage_refresh_runner.py:49: AssertionError
________ test_app_export_body_tolerates_signal_task_refresh_wait_error _________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

fut = <coroutine object Event.wait at 0x7f6cbebbd380>
timeout = 2.500966002000496

    async def wait_for(fut, timeout):
        """Wait for the single Future or coroutine to complete, with timeout.
    
        Coroutine will be wrapped in Task.
    
        Returns result of the Future or coroutine.  When a timeout occurs,
        it cancels the task and raises TimeoutError.  To avoid the task
        cancellation, wrap it in shield().
    
        If the wait is cancelled, the task is also cancelled.
    
        If the task suppresses the cancellation and returns a value instead,
        that value is returned.
    
        This function is a coroutine.
        """
        # The special case for timeout <= 0 is for the following case:
        #
        # async def test_waitfor():
        #     func_started = False
        #
        #     async def func():
        #         nonlocal func_started
        #         func_started = True
        #
        #     try:
        #         await asyncio.wait_for(func(), 0)
        #     except asyncio.TimeoutError:
        #         assert not func_started
        #     else:
        #         assert False
        #
        # asyncio.run(test_waitfor())
    
    
        if timeout is not None and timeout <= 0:
            fut = ensure_future(fut)
    
            if fut.done():
                return fut.result()
    
            await _cancel_and_wait(fut)
            try:
                return fut.result()
            except exceptions.CancelledError as exc:
                raise TimeoutError from exc
    
        async with timeouts.timeout(timeout):
>           return await fut
                   ^^^^^^^^^

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/asyncio/tasks.py:488: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <asyncio.locks.Event object at 0x7f6ce917cdd0 [set]>

    async def wait(self):
        """Block until the internal flag is true.
    
        If the internal flag is true on entry, return True
        immediately.  Otherwise, block until another task calls
        set() to set the flag to true, then return True.
        """
        if self._value:
            return True
    
        fut = self._get_loop().create_future()
        self._waiters.append(fut)
        try:
>           await fut
E           asyncio.exceptions.CancelledError

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/asyncio/locks.py:213: CancelledError

The above exception was the direct cause of the following exception:

self = AceApp(title='sase tui (v0.18.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
deadline = 35144.503565081

    async def _wait_for_screenshot_refresh_until(self, deadline: float) -> None:
        """Wait for one refresh without letting it outlive the settle deadline."""
        loop = asyncio.get_running_loop()
        remaining = deadline - loop.time()
        if remaining <= 0:
            raise RuntimeError(
                "timed out before requesting screenshot refresh; "
                f"deadline={_SCREENSHOT_SETTLE_TIMEOUT_SECONDS:.3f}s"
            )
        call_after_refresh = getattr(self, "call_after_refresh", None)
        if callable(call_after_refresh):
            acknowledged = asyncio.Event()
    
            def acknowledge_refresh() -> None:
                acknowledged.set()
    
            try:
                call_after_refresh(acknowledge_refresh)
            except (AssertionError, RuntimeError) as exc:
                raise RuntimeError(
                    "failed to schedule screenshot refresh acknowledgement: "
                    f"{type(exc).__name__}: {exc}"
                ) from exc
            self._request_screenshot_refresh_if_available()
            try:
>               await asyncio.wait_for(acknowledged.wait(), timeout=remaining)

src/sase/ace/tui/actions/screenshot_export.py:246: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/asyncio/tasks.py:487: in wait_for
    async with timeouts.timeout(timeout):
               ^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Timeout [expired]>
exc_type = <class 'asyncio.exceptions.CancelledError'>
exc_val = CancelledError(), exc_tb = <traceback object at 0x7f6ce9370180>

    async def __aexit__(
        self,
        exc_type: type[BaseException] | None,
        exc_val: BaseException | None,
        exc_tb: TracebackType | None,
    ) -> bool | None:
        assert self._state in (_State.ENTERED, _State.EXPIRING)
    
        if self._timeout_handler is not None:
            self._timeout_handler.cancel()
            self._timeout_handler = None
    
        if self._state is _State.EXPIRING:
            self._state = _State.EXPIRED
    
            if self._task.uncancel() <= self._cancelling and exc_type is not None:
                # Since there are no new cancel requests, we're
                # handling this.
                if issubclass(exc_type, exceptions.CancelledError):
>                   raise TimeoutError from exc_val
E                   TimeoutError

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/asyncio/timeouts.py:115: TimeoutError

The above exception was the direct cause of the following exception:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw4/test_app_export_body_tolerates0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6cdb2ecbb0>

    async def test_app_export_body_tolerates_signal_task_refresh_wait_error(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        async with AcePage() as page:
    
            async def fail_wait_for_refresh() -> None:
                raise AssertionError("Node must be running before calling wait_for_refresh")
    
            monkeypatch.setattr(page.app, "wait_for_refresh", fail_wait_for_refresh)
>           paths = await page.app._run_screenshot_export(tmp_path)
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_screenshot_export.py:524: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/screenshot_export.py:144: in _run_screenshot_export
    svg = await self._export_settled_screenshot_svg()
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/actions/screenshot_export.py:193: in _export_settled_screenshot_svg
    await self._wait_for_screenshot_refresh_until(deadline)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase tui (v0.18.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
deadline = 35144.503565081

    async def _wait_for_screenshot_refresh_until(self, deadline: float) -> None:
        """Wait for one refresh without letting it outlive the settle deadline."""
        loop = asyncio.get_running_loop()
        remaining = deadline - loop.time()
        if remaining <= 0:
            raise RuntimeError(
                "timed out before requesting screenshot refresh; "
                f"deadline={_SCREENSHOT_SETTLE_TIMEOUT_SECONDS:.3f}s"
            )
        call_after_refresh = getattr(self, "call_after_refresh", None)
        if callable(call_after_refresh):
            acknowledged = asyncio.Event()
    
            def acknowledge_refresh() -> None:
                acknowledged.set()
    
            try:
                call_after_refresh(acknowledge_refresh)
            except (AssertionError, RuntimeError) as exc:
                raise RuntimeError(
                    "failed to schedule screenshot refresh acknowledgement: "
                    f"{type(exc).__name__}: {exc}"
                ) from exc
            self._request_screenshot_refresh_if_available()
            try:
                await asyncio.wait_for(acknowledged.wait(), timeout=remaining)
            except TimeoutError as exc:
>               raise RuntimeError(
                    "timed out waiting for screenshot refresh acknowledgement; "
                    f"deadline={_SCREENSHOT_SETTLE_TIMEOUT_SECONDS:.3f}s"
                ) from exc
E               RuntimeError: timed out waiting for screenshot refresh acknowledgement; deadline=3.000s

src/sase/ace/tui/actions/screenshot_export.py:248: RuntimeError
_ test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap _
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_weight_two_land_agent_ses0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f2bf60a9470>

    def test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A ``--next`` authored at creation is dispatched by the real settlement
        path into a controlled fakey successor, and a weight-2 competitor stays
        parked -- proving a gapless handoff -- through the starter's release and
        the monitor's own real completion.
    
        Unlike the former hand-authored variant, ``next_action`` is authored on
        the monitor's own persisted proc request at creation (never injected into
        an in-memory copy afterward), dispatch is driven by the real
        ``settle_named_proc`` -> ``launch_followup_agent`` ->
        ``claim_ordinary_continuation_dispatch`` reservation/adoption path (only
        the low-level OS process spawn is faked, the same seam every monitor
        lifecycle test in this suite uses), and the successor's weight/priority
        are parsed from its real ``%queue`` prompt prefix rather than hard-coded
        in the spawn stub.
    
        The competitor is released -- not killed -- immediately before the real
        dispatch call, rather than before the monitor's own completion as the
        former variant did: this test found that a competitor left polling
        through the successor's own admission reliably wins that specific
        window (its already-hot poll loop beats the brand-new successor
        thread's first scan), which a fresh weight-2 waiter introduced only
        once the successor is confirmed live cannot do. See PROPOSED FOLLOW-UP
        on this bead for the reproducible gap this uncovered in the
        monitor-to-successor handoff specifically (the starter-to-monitor
        handoff proven gapless above is unaffected).
        """
        import tests.fakey._runner_slot_harness as harness_module
    
        monkeypatch.setattr(harness_module, "_WAIT_TIMEOUT", 5.0)
        monkeypatch.setattr(harness_module, "_FAKEY_RELEASE_TIMEOUT", 5.0)
        harness = _RunnerSlotFakeyHarness(tmp_path, monkeypatch, cap=2)
        monkeypatch.delenv("SASE_AGENT_NAME", raising=False)
        write_project_file(_MONITOR_PROJECT, workspace_dir=str(harness.workspace))
    
        starter = harness.create_agent(
            0,
            name="land--0",
            agent_session="land",
            queue_weight=2.0,
            queue_weight_explicit=True,
        )
        # `%i(@, session=...)` resolution (exercised below by the real ``--next``
        # handoff) matches on `workflow_name`, the durable agent-session key -- not on
        # `agent_session` alone -- so a real starter must carry both. A real
        # starter also always carries its own continuation-graph node id from
        # its own captured turn; without one, monitor-result capture treats the
        # starter link as broken and blocks automatic dispatch outright.
        starter.meta["workflow_name"] = "land"
        starter.meta["continuation_node_id"] = "agent-turn:land--0:sentinel"
        write_agent_meta(str(starter.artifacts_dir), starter.meta)
        harness.start(starter)
        harness.wait_started(starter)
        starter_owner_key = harness.agent_meta(starter).get("runner_claim_owner_key")
        assert isinstance(starter_owner_key, str) and starter_owner_key
    
        competitor = harness.create_agent(
            1, name="competitor", queue_weight=2.0, queue_weight_explicit=True
        )
        harness.start(competitor)
        harness.wait_parked(competitor)
    
        patch_project_records(monkeypatch, [str(starter.artifacts_dir)])
        # A real, currently-live (but otherwise unrelated) dummy process stands
        # in for the detached supervisor's PID: the weighted-capacity liveness
        # check must see the monitor's claim as genuinely live throughout.
        dummy_supervisor = subprocess.Popen(
            [sys.executable, "-c", "import time; time.sleep(30)"]
        )
        monkeypatch.setattr(
            spawn_module.subprocess, "Popen", make_bootstrap_popen(dummy_supervisor.pid)
        )
    
        try:
            # `next_action` is authored right here, at creation, on the request
            # the real proc-supervisor settlement path reads back from disk --
            # never injected into an in-memory metadata copy after the fact.
            record = start_monitor(
                StartMonitorRequest(
                    command="true",
                    reason="weight-2 land agent-session acceptance",
                    timeout_seconds=30.0,
                    cwd=str(harness.workspace),
                    project_name=_MONITOR_PROJECT,
                    start_status="MONITORING",
                    stop_status="MONITORED",
                    lane="land",
                    inherit_lane_workspace_claim=False,
                    next_action="Report that the land agent session finished.",
                )
            )
    
            monitor_meta = json.loads(
                (Path(record.artifacts_dir) / "agent_meta.json").read_text(encoding="utf-8")
            )
            assert monitor_meta["runner_claim_owner_key"] == starter_owner_key
            assert monitor_meta["queue_weight"] == 2.0
            assert monitor_meta["queue_weight_explicit"] is True
    
            # Production kills the starter's runner group as part of a real
            # handoff; release its fakey process so only the monitor represents
            # live lineage.
            harness.release_agent(starter)
>           harness.join(starter)

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/fakey/test_monitor_capacity_e2e.py:210: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <tests.fakey._runner_slot_harness._RunnerSlotFakeyHarness object at 0x7f2c18ddbc50>
agent = _Agent(name='land--0', artifacts_dir=PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_weight...t=2.0, queue_weight_explicit=True, crash=False, killed=False, thread=<Thread(land--0, stopped daemon 139826670065344)>)

    def join(self, agent: _Agent) -> None:
        assert agent.thread is not None
        agent.thread.join(_WAIT_TIMEOUT)
        assert not agent.thread.is_alive(), (
            f"agent {agent.name} did not finish; {self._diagnostics(agent)}"
        )
        errors = [error for name, error in self._errors if name == agent.name]
>       assert not errors, f"agent {agent.name} failed: {errors!r}"
               ^^^^^^^^^^
E       AssertionError: agent land--0 failed: [CalledProcessError(124, ['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/fakey', '--model', 'fakey-large'])]

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/fakey/_runner_slot_harness.py:241: AssertionError
----------------------------- Captured stdout call -----------------------------
Waiting for a runner slot
__________ test_muse_usage_probe_mints_with_the_minimal_echo_sequence __________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_mints_wi0')

    def test_muse_usage_probe_mints_with_the_minimal_echo_sequence(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        result, messages, argv = _run_muse_probe(fake, tmp_path)
    
        methods = _methods(messages)
>       assert methods[: len(_SEQUENCE_PREFIX)] == _SEQUENCE_PREFIX
E       AssertionError: assert [] == ['initialize'... 'turn/start']
E         
E         Right contains 4 more items, first extra item: 'initialize'
E         Use -v to get more diff

tests/llm_provider/test_muse_usage_probe.py:144: AssertionError
_______ test_muse_usage_probe_scopes_the_session_to_the_probe_directory ________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_scopes_t0')

    def test_muse_usage_probe_scopes_the_session_to_the_probe_directory(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        scratch = tmp_path / "scratch"
        scratch.mkdir()
        _, messages, argv = _run_muse_probe(fake, tmp_path, working_directory=str(scratch))
        assert argv[0]["cwd"] == str(scratch)
>       assert messages[2]["params"]["workspaceRoot"] == str(scratch)
               ^^^^^^^^^^^
E       IndexError: list index out of range

tests/llm_provider/test_muse_usage_probe.py:190: IndexError
____________ test_muse_usage_probe_preserves_over_quota_percentages ____________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_preserve0')

    def test_muse_usage_probe_preserves_over_quota_percentages(tmp_path: Path) -> None:
        fake = _make_fake_muse(tmp_path)
        over_quota = {
            **_LIVE_USAGE,
            "weekly": {"resetsAtMs": 1789948800000, "usedPercent": 130},
        }
        result, _, _ = _run_muse_probe(fake, tmp_path, usage=over_quota)
>       session, weekly = result["windows"]
        ^^^^^^^^^^^^^^^
E       ValueError: not enough values to unpack (expected 2, got 0)

tests/llm_provider/test_muse_usage_probe.py:200: ValueError
_________ test_muse_usage_probe_malformed_usage_is_a_structured_error __________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_malforme0')

    def test_muse_usage_probe_malformed_usage_is_a_structured_error(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        result, _, _ = _run_muse_probe(fake, tmp_path, usage="not-an-object")
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "malformed_payload"
E       AssertionError: assert 'timeout' == 'malformed_payload'
E         
E         - malformed_payload
E         + timeout

tests/llm_provider/test_muse_usage_probe.py:242: AssertionError
_ test_muse_usage_probe_aborts_before_any_turn_when_the_session_is_not_echo[guard_provider] _
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_aborts_b0')
mode = 'guard_provider'

    @pytest.mark.parametrize("mode", ["guard_provider", "guard_model"])
    def test_muse_usage_probe_aborts_before_any_turn_when_the_session_is_not_echo(
        tmp_path: Path, mode: str
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        result, messages, _ = _run_muse_probe(fake, tmp_path, mode=mode)
        # The frame log is the point: a turn against a real provider would spend
        # tokens on every refresh tick, so no ``turn/start`` may ever be sent.
>       assert _methods(messages) == ["initialize", "initialized", "session/start"]
E       AssertionError: assert [] == ['initialize'...ession/start']
E         
E         Right contains 3 more items, first extra item: 'initialize'
E         Use -v to get more diff

tests/llm_provider/test_muse_usage_probe.py:255: AssertionError
_ test_muse_usage_probe_aborts_before_any_turn_when_the_session_is_not_echo[guard_model] _
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_aborts_b1')
mode = 'guard_model'

    @pytest.mark.parametrize("mode", ["guard_provider", "guard_model"])
    def test_muse_usage_probe_aborts_before_any_turn_when_the_session_is_not_echo(
        tmp_path: Path, mode: str
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        result, messages, _ = _run_muse_probe(fake, tmp_path, mode=mode)
        # The frame log is the point: a turn against a real provider would spend
        # tokens on every refresh tick, so no ``turn/start`` may ever be sent.
>       assert _methods(messages) == ["initialize", "initialized", "session/start"]
E       AssertionError: assert ['initialize'] == ['initialize'...ession/start']
E         
E         Right contains 2 more items, first extra item: 'initialized'
E         Use -v to get more diff

tests/llm_provider/test_muse_usage_probe.py:255: AssertionError
_____ test_muse_usage_probe_session_without_a_session_object_is_malformed ______
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_session_0')

    def test_muse_usage_probe_session_without_a_session_object_is_malformed(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        result, messages, _ = _run_muse_probe(
            fake, tmp_path, mode="session_payload_missing"
        )
        assert "turn/start" not in _methods(messages)
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "malformed_payload"
E       AssertionError: assert 'timeout' == 'malformed_payload'
E         
E         - malformed_payload
E         + timeout

tests/llm_provider/test_muse_usage_probe.py:270: AssertionError
__________ test_muse_usage_probe_unexpected_turn_ack_is_vendor_drift ___________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_unexpect0')

    def test_muse_usage_probe_unexpected_turn_ack_is_vendor_drift(tmp_path: Path) -> None:
        fake = _make_fake_muse(tmp_path)
        result, messages, _ = _run_muse_probe(fake, tmp_path, mode="turn_ack_queued")
>       assert _methods(messages) == _SEQUENCE_PREFIX
E       AssertionError: assert [] == ['initialize'... 'turn/start']
E         
E         Right contains 4 more items, first extra item: 'initialize'
E         Use -v to get more diff

tests/llm_provider/test_muse_usage_probe.py:277: AssertionError
_____________ test_muse_usage_probe_rejected_turn_is_vendor_drift ______________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_rejected0')

    def test_muse_usage_probe_rejected_turn_is_vendor_drift(tmp_path: Path) -> None:
        fake = _make_fake_muse(tmp_path)
        result, messages, _ = _run_muse_probe(fake, tmp_path, mode="turn_rejected")
>       assert _methods(messages) == _SEQUENCE_PREFIX
E       AssertionError: assert [] == ['initialize'... 'turn/start']
E         
E         Right contains 4 more items, first extra item: 'initialize'
E         Use -v to get more diff

tests/llm_provider/test_muse_usage_probe.py:286: AssertionError
__________ test_muse_usage_probe_missing_usage_method_is_vendor_drift __________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_missing_0')

    def test_muse_usage_probe_missing_usage_method_is_vendor_drift(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        result, messages, _ = _run_muse_probe(fake, tmp_path, mode="usage_method_missing")
>       assert _methods(messages) == [*_SEQUENCE_PREFIX, "usage/read"]
E       AssertionError: assert [] == ['initialize'... 'usage/read']
E         
E         Right contains 5 more items, first extra item: 'initialize'
E         Use -v to get more diff

tests/llm_provider/test_muse_usage_probe.py:297: AssertionError
__________ test_muse_usage_probe_other_host_errors_are_probe_failures __________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_other_ho0')

    def test_muse_usage_probe_other_host_errors_are_probe_failures(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        result, _, _ = _run_muse_probe(fake, tmp_path, mode="usage_read_error")
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "probe_failed"
E       AssertionError: assert 'timeout' == 'probe_failed'
E         
E         - probe_failed
E         + timeout

tests/llm_provider/test_muse_usage_probe.py:309: AssertionError
____________ test_muse_usage_probe_rate_limit_error_is_rate_limited ____________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_rate_lim0')

    def test_muse_usage_probe_rate_limit_error_is_rate_limited(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        result, _, _ = _run_muse_probe(fake, tmp_path, mode="usage_rate_limited")
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "rate_limited"
E       AssertionError: assert 'timeout' == 'rate_limited'
E         
E         - rate_limited
E         + timeout

tests/llm_provider/test_muse_usage_probe.py:327: AssertionError
______ test_muse_transport_failure_with_rate_limit_stderr_is_rate_limited ______
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_transport_failure_wi0')

    def test_muse_transport_failure_with_rate_limit_stderr_is_rate_limited(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_muse(tmp_path)
        result, _, _ = _run_muse_probe(fake, tmp_path, mode="transport_rate_limited")
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "rate_limited"
E       AssertionError: assert 'timeout' == 'rate_limited'
E         
E         - rate_limited
E         + timeout

tests/llm_provider/test_muse_usage_probe.py:338: AssertionError
___________ test_muse_usage_probe_refuses_unsolicited_host_requests ____________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_muse_usage_probe_refuses_0')

    def test_muse_usage_probe_refuses_unsolicited_host_requests(tmp_path: Path) -> None:
        fake = _make_fake_muse(tmp_path)
        result, messages, _ = _run_muse_probe(fake, tmp_path, mode="unsolicited_request")
        # The request surfaces while the probe waits on its first ``usage/read``, and
        # an approval-style server request is never answered.
>       assert _methods(messages) == [*_SEQUENCE_PREFIX, "usage/read"]
E       AssertionError: assert ['initialize'] == ['initialize'... 'usage/read']
E         
E         Right contains 4 more items, first extra item: 'initialized'
E         Use -v to get more diff

tests/llm_provider/test_muse_usage_probe.py:348: AssertionError
_____ test_zero_weight_wait_monitor_followup_reenters_full_host_admission ______
[gw17] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw17/test_zero_weight_wait_monitor_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f91804a1940>

    def test_zero_weight_wait_monitor_followup_reenters_full_host_admission(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """The monitor is free, but its weight-2 successor waits for real capacity."""
        import tests.fakey._runner_slot_harness as harness_module
    
        monkeypatch.setattr(harness_module, "_WAIT_TIMEOUT", 5.0)
        # Follow-up dispatch has a bounded 60-second starter-settle window; keep
        # the already-admitted filler alive through that production wait.
        monkeypatch.setattr(harness_module, "_FAKEY_RELEASE_TIMEOUT", 90.0)
        harness = _RunnerSlotFakeyHarness(tmp_path, monkeypatch, cap=2)
        for name in ("SASE_AGENT", "SASE_AGENT_NAME"):
            monkeypatch.delenv(name, raising=False)
        write_project_file(_MONITOR_PROJECT, workspace_dir=str(harness.workspace))
    
        starter = harness.create_agent(
            0,
            name="wait--0",
            agent_session="wait",
            queue_weight=2.0,
            queue_weight_explicit=True,
        )
        starter.meta["workflow_name"] = "wait"
        starter.meta["continuation_node_id"] = "agent-turn:wait--0:sentinel"
        write_agent_meta(str(starter.artifacts_dir), starter.meta)
        harness.start(starter)
        harness.wait_started(starter)
    
        patch_project_records(monkeypatch, [str(starter.artifacts_dir)])
        dummy_supervisor = subprocess.Popen(
            [sys.executable, "-c", "import time; time.sleep(30)"]
        )
        monkeypatch.setattr(
            spawn_module.subprocess, "Popen", make_bootstrap_popen(dummy_supervisor.pid)
        )
    
        filler: _Agent | None = None
        successor: _Agent | None = None
        competitor: _Agent | None = None
        try:
            record = start_monitor(
                StartMonitorRequest(
                    command="true",
                    reason="zero-weight pure wait capacity acceptance",
                    timeout_seconds=30.0,
                    cwd=str(harness.workspace),
                    project_name=_MONITOR_PROJECT,
                    start_status="WAITING",
                    stop_status="WAITED",
                    lane="wait",
                    inherit_lane_workspace_claim=False,
                    next_action="Report that the external wait finished.",
                    queue_weight_override=0.0,
                )
            )
            monitor_meta = json.loads(
                (Path(record.artifacts_dir) / "agent_meta.json").read_text(encoding="utf-8")
            )
            assert monitor_meta["queue_weight"] == 0.0
            assert monitor_meta["queue_weight_explicit"] is True
            assert monitor_meta["monitor_queue_weight_overridden"] is True
            assert monitor_meta["monitor_inherited_queue_weight"] == 2.0
    
            harness.release_agent(starter)
            harness.join(starter)
    
            filler = harness.create_agent(
                1,
                name="filler",
                queue_weight=2.0,
                queue_weight_explicit=True,
            )
            harness.start(filler)
            harness.wait_started(filler)
    
            saved: dict[str, object] = {}
    
            def fake_spawn(**kwargs: object) -> AgentLaunchResult:
                nonlocal successor
                prompt = kwargs["prompt"]
                assert isinstance(prompt, str)
                _cleaned, directives = extract_prompt_directives(prompt)
                assert directives.queue_weight == 2.0
                assert directives.queue_weight_explicit is True
    
                extra_env = kwargs["extra_env"]
                assert isinstance(extra_env, dict)
                plan = json.loads(extra_env["SASE_AGENT_SESSION_ATTACH"])
                successor = harness.create_agent(
                    2,
                    name=plan["agent_name"],
                    parent_timestamp=Path(record.artifacts_dir).name,
                    agent_session="wait",
                    queue_weight=directives.queue_weight or 1.0,
                    queue_weight_explicit=directives.queue_weight_explicit,
                    wait_priority=directives.wait_priority,
                    wait_runners=directives.queue_capacity,
                )
                harness.start(successor)
                harness.wait_parked(successor)
                saved["env"] = dict(extra_env)
                saved["agent_name"] = plan["agent_name"]
                return AgentLaunchResult(
                    pid=os.getpid(),
                    workspace_num=0,
                    workspace_dir=str(harness.workspace),
                    output_path=str(harness.root / "monitor-successor.log"),
                    agent_name=plan["agent_name"],
                )
    
            monkeypatch.setattr(
                monitor_followup_module, "spawn_agent_subprocess", fake_spawn
            )
            settle_named_proc(
                record.monitor_id,
                supervisor_id="test-supervisor",
                status="success",
                message="completed",
                termination_reason="success",
                exit_code=0,
            )
            assert wait_for_done(record.artifacts_dir)["monitor_state"] == "completed"
            assert successor is not None
            harness.assert_parked_not_started(successor)
    
            harness.release_agent(filler)
            harness.join(filler)
            harness.wait_started(successor)
            adopted = adopt_ordinary_continuation_delivery(
                env=saved["env"], agent_name=str(saved["agent_name"])
            )
            assert adopted is not None
            assert adopted["disposition"] == "acknowledged"
    
            successor_meta = harness.agent_meta(successor)
            assert successor_meta["queue_weight"] == 2.0
            assert successor_meta["queue_weight_explicit"] is True
    
            competitor = harness.create_agent(
                3,
                name="late-competitor",
                queue_weight=2.0,
                queue_weight_explicit=True,
            )
            harness.start(competitor)
            harness.wait_parked(competitor)
            harness.release_agent(successor)
>           harness.join(successor)

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/fakey/test_monitor_capacity_zero_weight_wait_e2e.py:181: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <tests.fakey._runner_slot_harness._RunnerSlotFakeyHarness object at 0x7f91896a9e80>
agent = _Agent(name='wait--1', artifacts_dir=PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw17/test_zero_w...t=2.0, queue_weight_explicit=True, crash=False, killed=False, thread=<Thread(wait--1, stopped daemon 140262908794560)>)

    def join(self, agent: _Agent) -> None:
        assert agent.thread is not None
        agent.thread.join(_WAIT_TIMEOUT)
>       assert not agent.thread.is_alive(), (
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^
            f"agent {agent.name} did not finish; {self._diagnostics(agent)}"
        )
E       AssertionError: agent wait--1 did not finish; agent='wait--1' started=True parked=False released=True thread_alive=True claim_order=['wait--0', 'filler', 'wait--1'] errors=[]

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/fakey/_runner_slot_harness.py:237: AssertionError
----------------------------- Captured stdout call -----------------------------
{"context": "monitor-settlement", "event": "launch_scratch_cleanup", "reason": "no-matching-candidates", "removed": 0, "removed_bytes": 0, "scratch_key": "gh_sase-org__sase-ws0-261107_110646", "skipped": 0, "status": "skipped"}
Waiting for a runner slot
Waiting for a runner slot
_____________ test_grok_usage_probe_collects_native_weekly_billing _____________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_collects0')

    def test_grok_usage_probe_collects_native_weekly_billing(tmp_path: Path) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "creditUsagePercent": 37.5,
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                },
                "monthlyLimit": {"val": 1000},
                "used": 900,
                "onDemandEnabled": True,
                "prepaidBalance": 1234,
                "history": [{"amount": 1}],
                "subscriptionTier": "SuperGrok Heavy",
            }
        }
        result, messages, argv = _run_grok_probe(fake, tmp_path, payload)
>       window = result["windows"][0]
                 ^^^^^^^^^^^^^^^^^^^^
E       IndexError: list index out of range

tests/llm_provider/test_grok_usage_probe.py:132: IndexError
_________ test_grok_usage_probe_decodes_verified_legacy_monthly_ratio __________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_decodes_0')

    def test_grok_usage_probe_decodes_verified_legacy_monthly_ratio(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "monthlyLimit": {"val": 2000},
                "used": {"val": 500},
                "billingPeriodStart": "2027-01-01T00:00:00Z",
                "billingPeriodEnd": "2027-02-01T00:00:00Z",
                "subscriptionTier": "SuperGrok",
            }
        }
        result, _, _ = _run_grok_probe(fake, tmp_path, payload)
>       window = result["windows"][0]
                 ^^^^^^^^^^^^^^^^^^^^
E       IndexError: list index out of range

tests/llm_provider/test_grok_usage_probe.py:171: IndexError
_________ test_grok_usage_probe_missing_billing_method_is_vendor_drift _________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_missing_0')

    def test_grok_usage_probe_missing_billing_method_is_vendor_drift(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        result, messages, _ = _run_grok_probe(fake, tmp_path, mode="method_missing")
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "vendor_drift"
E       AssertionError: assert 'timeout' == 'vendor_drift'
E         
E         - vendor_drift
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:185: AssertionError
____________ test_grok_usage_probe_auth_required_is_unauthenticated ____________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_auth_req0')

    def test_grok_usage_probe_auth_required_is_unauthenticated(tmp_path: Path) -> None:
        fake = _make_fake_grok(tmp_path)
        result, _ = _run_grok_probe(fake, tmp_path, mode="auth_required")[:2]
>       assert result["outcome"] == "unauthenticated"
E       AssertionError: assert 'error' == 'unauthenticated'
E         
E         - unauthenticated
E         + error

tests/llm_provider/test_grok_usage_probe.py:196: AssertionError
_______________ test_grok_usage_probe_rate_limit_is_rate_limited _______________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_rate_lim0')

    def test_grok_usage_probe_rate_limit_is_rate_limited(tmp_path: Path) -> None:
        fake = _make_fake_grok(tmp_path)
        result, _ = _run_grok_probe(fake, tmp_path, mode="rate_limited")[:2]
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "rate_limited"
E       AssertionError: assert 'timeout' == 'rate_limited'
E         
E         - rate_limited
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:204: AssertionError
________________ test_startup_update_toast_appears_once_in_tui _________________
[gw23] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6d89c0be00>

    async def test_startup_update_toast_appears_once_in_tui(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_startup_loaders(monkeypatch)
        status = _status()
        monkeypatch.setattr(
            update_toast,
            "_load_update_toast_config",
            lambda: update_toast._UpdateToastConfig(startup_toast=True),
        )
        monkeypatch.setattr(
            update_toast,
            "get_cached_update_status",
            lambda **_kwargs: status,
        )
    
        async with AcePage(query='"toast"', startup_policy="real") as page:
>           await page.wait_for(lambda _s: bool(list(page.app._notifications)))

tests/ace/tui/test_update_toast_startup.py:166: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:558: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f6dac76afb0>

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
E               AssertionError: wait_for() timed out after 5.0s — predicate never returned True

src/sase/ace/testing/wait.py:54: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:295 TUI message pump stall detected: 5.376s pid=4103286
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:321 TUI message pump recovered after 6.175s
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:241 TUI event loop stall detected: 11.539s pid=4103286
WARNING  sase.ace.tui.util.stall_watchdog:_stall_watchdog_records.py:267 TUI event loop recovered after 12.060s
______ test_grok_transport_failure_with_rate_limit_stderr_is_rate_limited ______
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_transport_failure_wi0')

    def test_grok_transport_failure_with_rate_limit_stderr_is_rate_limited(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        result, _ = _run_grok_probe(fake, tmp_path, mode="transport_rate_limited")[:2]
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "rate_limited"
E       AssertionError: assert 'timeout' == 'rate_limited'
E         
E         - rate_limited
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:215: AssertionError
_ test_grok_usage_probe_explicit_ineligible_accounts_are_not_applicable[Free] __
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_explicit0')
tier = 'Free'

    @pytest.mark.parametrize("tier", ["Free", "Enterprise"])
    def test_grok_usage_probe_explicit_ineligible_accounts_are_not_applicable(
        tmp_path: Path, tier: str
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {"config": None, "subscriptionTier": tier}
        result, _ = _run_grok_probe(fake, tmp_path, payload)[:2]
>       assert result["outcome"] == "not_applicable"
E       AssertionError: assert 'error' == 'not_applicable'
E         
E         - not_applicable
E         + error

tests/llm_provider/test_grok_usage_probe.py:238: AssertionError
_ test_grok_usage_probe_explicit_ineligible_accounts_are_not_applicable[Enterprise] _
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_explicit1')
tier = 'Enterprise'

    @pytest.mark.parametrize("tier", ["Free", "Enterprise"])
    def test_grok_usage_probe_explicit_ineligible_accounts_are_not_applicable(
        tmp_path: Path, tier: str
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {"config": None, "subscriptionTier": tier}
        result, _ = _run_grok_probe(fake, tmp_path, payload)[:2]
>       assert result["outcome"] == "not_applicable"
E       AssertionError: assert 'error' == 'not_applicable'
E         
E         - not_applicable
E         + error

tests/llm_provider/test_grok_usage_probe.py:238: AssertionError
__________ test_grok_usage_probe_api_auth_evidence_is_not_applicable ___________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_api_auth0')

    def test_grok_usage_probe_api_auth_evidence_is_not_applicable(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {"config": None, "authMode": "api_key"}
        result, _ = _run_grok_probe(fake, tmp_path, payload)[:2]
>       assert result["outcome"] == "not_applicable"
E       AssertionError: assert 'error' == 'not_applicable'
E         
E         - not_applicable
E         + error

tests/llm_provider/test_grok_usage_probe.py:248: AssertionError
______ test_grok_usage_probe_absent_config_without_evidence_is_malformed _______
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_absent_c0')

    def test_grok_usage_probe_absent_config_without_evidence_is_malformed(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        result, _ = _run_grok_probe(fake, tmp_path, {"config": None})[:2]
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "malformed_payload"
E       AssertionError: assert 'timeout' == 'malformed_payload'
E         
E         - malformed_payload
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:258: AssertionError
____________ test_grok_usage_probe_identity_mismatch_is_unsupported ____________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_identity0')

    def test_grok_usage_probe_identity_mismatch_is_unsupported(tmp_path: Path) -> None:
        fake = _make_fake_grok(tmp_path)
        result, messages, argv = _run_grok_probe(
            fake, tmp_path, {"config": None}, version="not-grok 0.1.0"
        )
>       assert result["outcome"] == "unsupported"
E       AssertionError: assert 'error' == 'unsupported'
E         
E         - unsupported
E         + error

tests/llm_provider/test_grok_usage_probe.py:266: AssertionError
_______________ test_grok_usage_probe_missing_period_is_partial ________________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_missing_1')

    def test_grok_usage_probe_missing_period_is_partial(tmp_path: Path) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "creditUsagePercent": 12.0,
                "subscriptionTier": "SuperGrok",
            }
        }
        result, _ = _run_grok_probe(fake, tmp_path, payload)[:2]
>       window = result["windows"][0]
                 ^^^^^^^^^^^^^^^^^^^^
E       IndexError: list index out of range

tests/llm_provider/test_grok_usage_probe.py:281: IndexError
____________ test_grok_usage_probe_missing_percentage_is_malformed _____________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_missing_2')

    def test_grok_usage_probe_missing_percentage_is_malformed(tmp_path: Path) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                }
            }
        }
        result, _ = _run_grok_probe(fake, tmp_path, payload)[:2]
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "malformed_payload"
E       AssertionError: assert 'timeout' == 'malformed_payload'
E         
E         - malformed_payload
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:303: AssertionError
__________ test_start_monitor_reparents_the_supervisor_before_return ___________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_start_monitor_reparents_t0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f415995cad0>

    @pytest.mark.skipif(not Path("/proc").is_dir(), reason="/proc ancestry is required")
    def test_start_monitor_reparents_the_supervisor_before_return(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        write_project_file("proj")
        starter_dir = make_starter_agent(
            "proj",
            "20260812120000",
            "acme--0",
            agent_session="acme",
            model="claude-sonnet-5",
            workspace_dir=str(tmp_path),
            workspace_num=0,
            pid=os.getpid(),
            cl_name="acme",
        )
        patch_project_records(monkeypatch, [starter_dir])
    
        record = start_monitor(
            StartMonitorRequest(
                command="sleep 30",
                reason="verify reparenting",
                timeout_seconds=120.0,
                cwd=str(tmp_path),
                project_name="proj",
                start_status="MONITORING",
                stop_status="MONITORED",
                lane="acme",
                inherit_lane_workspace_claim=False,
            )
        )
    
        try:
            assert record.pid is not None
            assert os.getpid() not in _ancestor_pids(record.pid)
        finally:
            if record.pid is not None:
                os.kill(record.pid, signal.SIGTERM)
>           wait_for_done(record.artifacts_dir, timeout=10.0)

tests/monitor/test_monitor_start_supervisor.py:294: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_start_monitor_reparents_t0/.sase/projects/proj/artifacts/ace-run/202611/07/20261107160148'

    def wait_for_done(
        artifacts_dir: str,
        *,
        timeout: float = POLL_TIMEOUT,
    ) -> dict[str, object]:
        """Block until a monitor member writes ``done.json`` and return it."""
        done_path = Path(artifacts_dir) / "done.json"
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            if done_path.exists():
                try:
                    return json.loads(done_path.read_text())
                except json.JSONDecodeError:
                    pass
            time.sleep(POLL_INTERVAL)
>       raise AssertionError(f"monitor at {artifacts_dir} never finished")
E       AssertionError: monitor at /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_start_monitor_reparents_t0/.sase/projects/proj/artifacts/ace-run/202611/07/20261107160148 never finished

tests/monitor/_fixtures.py:177: AssertionError
_____ test_grok_usage_probe_omitted_zero_unified_weekly_is_complete[None] ______
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_omitted_0')
result_wrap = None

    @pytest.mark.parametrize("result_wrap", [None, "string", "nested"])
    def test_grok_usage_probe_omitted_zero_unified_weekly_is_complete(
        tmp_path: Path, result_wrap: str | None
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        result, _, _ = _run_grok_probe(
            fake, tmp_path, _unified_omitted_zero_payload(), result_wrap=result_wrap
        )
>       window = result["windows"][0]
                 ^^^^^^^^^^^^^^^^^^^^
E       IndexError: list index out of range

tests/llm_provider/test_grok_usage_probe.py:333: IndexError
____ test_grok_usage_probe_omitted_zero_unified_weekly_is_complete[string] _____
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_omitted_1')
result_wrap = 'string'

    @pytest.mark.parametrize("result_wrap", [None, "string", "nested"])
    def test_grok_usage_probe_omitted_zero_unified_weekly_is_complete(
        tmp_path: Path, result_wrap: str | None
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        result, _, _ = _run_grok_probe(
            fake, tmp_path, _unified_omitted_zero_payload(), result_wrap=result_wrap
        )
>       window = result["windows"][0]
                 ^^^^^^^^^^^^^^^^^^^^
E       IndexError: list index out of range

tests/llm_provider/test_grok_usage_probe.py:333: IndexError
____ test_grok_usage_probe_omitted_zero_unified_weekly_is_complete[nested] _____
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_omitted_2')
result_wrap = 'nested'

    @pytest.mark.parametrize("result_wrap", [None, "string", "nested"])
    def test_grok_usage_probe_omitted_zero_unified_weekly_is_complete(
        tmp_path: Path, result_wrap: str | None
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        result, _, _ = _run_grok_probe(
            fake, tmp_path, _unified_omitted_zero_payload(), result_wrap=result_wrap
        )
>       window = result["windows"][0]
                 ^^^^^^^^^^^^^^^^^^^^
E       IndexError: list index out of range

tests/llm_provider/test_grok_usage_probe.py:333: IndexError
____ test_ppid_walk_teardown_of_starter_descendants_leaves_monitor_running _____
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_ppid_walk_teardown_of_sta0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f415995f850>

    @pytest.mark.skipif(not Path("/proc").is_dir(), reason="/proc ancestry is required")
    def test_ppid_walk_teardown_of_starter_descendants_leaves_monitor_running(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        write_project_file("proj")
        starter_dir = make_starter_agent(
            "proj",
            "20260812120000",
            "acme--0",
            agent_session="acme",
            model="claude-sonnet-5",
            workspace_dir=str(tmp_path),
            workspace_num=0,
            pid=os.getpid(),
            cl_name="acme",
        )
        patch_project_records(monkeypatch, [starter_dir])
        command = _python_command(
            "import time; print('survived teardown', flush=True); "
            "time.sleep(0.2); print('finished', flush=True)"
        )
    
        record = start_monitor(
            StartMonitorRequest(
                command=command,
                reason="verify ppid walk survival",
                timeout_seconds=30.0,
                cwd=str(tmp_path),
                project_name="proj",
                start_status="MONITORING",
                stop_status="MONITORED",
                lane="acme",
                inherit_lane_workspace_claim=False,
            )
        )
    
        _signal_descendants(os.getpid(), signal.SIGTERM)
    
>       done = wait_for_done(record.artifacts_dir, timeout=10.0)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/monitor/test_monitor_start_supervisor.py:335: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_ppid_walk_teardown_of_sta0/.sase/projects/proj/artifacts/ace-run/202611/07/20261107160208'

    def wait_for_done(
        artifacts_dir: str,
        *,
        timeout: float = POLL_TIMEOUT,
    ) -> dict[str, object]:
        """Block until a monitor member writes ``done.json`` and return it."""
        done_path = Path(artifacts_dir) / "done.json"
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            if done_path.exists():
                try:
                    return json.loads(done_path.read_text())
                except json.JSONDecodeError:
                    pass
            time.sleep(POLL_INTERVAL)
>       raise AssertionError(f"monitor at {artifacts_dir} never finished")
E       AssertionError: monitor at /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_ppid_walk_teardown_of_sta0/.sase/projects/proj/artifacts/ace-run/202611/07/20261107160208 never finished

tests/monitor/_fixtures.py:177: AssertionError
_____ test_grok_usage_probe_omitted_zero_unified_monthly_and_explicit_zero _____
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_omitted_3')

    def test_grok_usage_probe_omitted_zero_unified_monthly_and_explicit_zero(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        monthly = {
            "subscription_tier": "SuperGrok Heavy",
            "config": {
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_MONTHLY",
                    "start": "2027-01-01T00:00:00Z",
                    "end": "2027-02-01T00:00:00Z",
                },
                "isUnifiedBillingUser": True,
            },
        }
        explicit = {
            "subscription_tier": "SuperGrok Heavy",
            "config": {
                "creditUsagePercent": 0.0,
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                },
                "isUnifiedBillingUser": True,
            },
        }
        monthly_result, _, _ = _run_grok_probe(fake, tmp_path, monthly)
        explicit_result, _, _ = _run_grok_probe(fake, tmp_path, explicit)
>       assert monthly_result["windows"][0]["key"] == "included_monthly"
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       IndexError: list index out of range

tests/llm_provider/test_grok_usage_probe.py:378: IndexError
_____________ test_sighup_to_supervisor_does_not_stop_the_monitor ______________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_sighup_to_supervisor_does0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f41708a80c0>

    def test_sighup_to_supervisor_does_not_stop_the_monitor(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        ready_file = tmp_path / "ready"
        write_project_file("proj")
        starter_dir = make_starter_agent(
            "proj",
            "20260812120000",
            "acme--0",
            agent_session="acme",
            model="claude-sonnet-5",
            workspace_dir=str(tmp_path),
            workspace_num=0,
            pid=os.getpid(),
            cl_name="acme",
        )
        patch_project_records(monkeypatch, [starter_dir])
        command = _python_command(
            f"from pathlib import Path; import time; "
            f"Path({str(ready_file)!r}).write_text('1'); "
            "print('ready', flush=True); time.sleep(0.5); print('done', flush=True)"
        )
    
        record = start_monitor(
            StartMonitorRequest(
                command=command,
                reason="verify sighup ignored",
                timeout_seconds=30.0,
                cwd=str(tmp_path),
                project_name="proj",
                start_status="MONITORING",
                stop_status="MONITORED",
                lane="acme",
                inherit_lane_workspace_claim=False,
            )
        )
    
        assert record.pid is not None
        wait_for_path(ready_file, timeout=10.0)
        os.kill(record.pid, signal.SIGHUP)
    
>       done = wait_for_done(record.artifacts_dir, timeout=10.0)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/monitor/test_monitor_start_supervisor.py:383: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_sighup_to_supervisor_does0/.sase/projects/proj/artifacts/ace-run/202611/07/20261107160223'

    def wait_for_done(
        artifacts_dir: str,
        *,
        timeout: float = POLL_TIMEOUT,
    ) -> dict[str, object]:
        """Block until a monitor member writes ``done.json`` and return it."""
        done_path = Path(artifacts_dir) / "done.json"
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            if done_path.exists():
                try:
                    return json.loads(done_path.read_text())
                except json.JSONDecodeError:
                    pass
            time.sleep(POLL_INTERVAL)
>       raise AssertionError(f"monitor at {artifacts_dir} never finished")
E       AssertionError: monitor at /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_sighup_to_supervisor_does0/.sase/projects/proj/artifacts/ace-run/202611/07/20261107160223 never finished

tests/monitor/_fixtures.py:177: AssertionError
_____________________ test_descendant_processes_are_reaped _____________________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6cc8185cc0>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw4/test_descendant_processes_are_0')

    def test_descendant_processes_are_reaped(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        monkeypatch.delenv("SASE_FEATURE_FLAGS", raising=False)
        pidfile = tmp_path / "child.pid"
        # This test proves descendant cleanup after timeout. Give a cold isolated
        # worker time to import the provider and write the PID file; the hanging-
        # plugin test covers the tighter production deadline path.
        context = default_probe_context("synth", deadline_seconds=5)
        result = run_usage_probe(
            context,
            isolate=True,
            plugin_spec=SYNTHETIC_PLUGIN_SPEC,
            env={
                SYNTHETIC_MODE_ENV: "descendants",
                SYNTHETIC_PIDFILE_ENV: str(pidfile),
            },
        )
        assert result.observation is not None
        assert result.observation["reason_code"] == "timeout"
>       child_pid = int(pidfile.read_text(encoding="utf-8"))
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/llm_provider/test_usage_probe.py:233: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pathlib/__init__.py:787: in read_text
    with self.open(mode='r', encoding=encoding, errors=errors, newline=newline) as f:
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw4/test_descendant_processes_are_0/child.pid')
mode = 'r', buffering = -1, encoding = 'utf-8', errors = None, newline = None

    def open(self, mode='r', buffering=-1, encoding=None,
             errors=None, newline=None):
        """
        Open the file pointed to by this path and return a file object, as
        the built-in open() function does.
        """
        if "b" not in mode:
            encoding = io.text_encoding(encoding)
>       return io.open(self, mode, buffering, encoding, errors, newline)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       FileNotFoundError: [Errno 2] No such file or directory: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw4/test_descendant_processes_are_0/child.pid'

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pathlib/__init__.py:771: FileNotFoundError
_______________ test_grok_usage_probe_empty_used_object_is_zero ________________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_empty_us0')

    def test_grok_usage_probe_empty_used_object_is_zero(tmp_path: Path) -> None:
        fake = _make_fake_grok(tmp_path)
        for used in ({}, {"val": 0}):
            payload = {
                "config": {
                    "monthlyLimit": {"val": 2000},
                    "used": used,
                    "billingPeriodStart": "2027-01-01T00:00:00Z",
                    "billingPeriodEnd": "2027-02-01T00:00:00Z",
                }
            }
            result, _, _ = _run_grok_probe(fake, tmp_path, payload)
>           assert result["outcome"] == "ok"
E           AssertionError: assert 'error' == 'ok'
E             
E             - ok
E             + error

tests/llm_provider/test_grok_usage_probe.py:396: AssertionError
______ test_grok_usage_probe_invalid_explicit_percent_is_malformed[None] _______
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_invalid_0')
percent = None

    @pytest.mark.parametrize(
        "percent",
        [None, True, "0", -1.0],
    )
    def test_grok_usage_probe_invalid_explicit_percent_is_malformed(
        tmp_path: Path, percent: object
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "creditUsagePercent": percent,
                "isUnifiedBillingUser": True,
                "monthlyLimit": {"val": 1000},
                "used": {"val": 0},
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                },
            }
        }
        result, _, _ = _run_grok_probe(fake, tmp_path, payload)
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "malformed_payload"
E       AssertionError: assert 'timeout' == 'malformed_payload'
E         
E         - malformed_payload
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:423: AssertionError
______ test_grok_usage_probe_invalid_explicit_percent_is_malformed[True] _______
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_invalid_1')
percent = True

    @pytest.mark.parametrize(
        "percent",
        [None, True, "0", -1.0],
    )
    def test_grok_usage_probe_invalid_explicit_percent_is_malformed(
        tmp_path: Path, percent: object
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "creditUsagePercent": percent,
                "isUnifiedBillingUser": True,
                "monthlyLimit": {"val": 1000},
                "used": {"val": 0},
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                },
            }
        }
        result, _, _ = _run_grok_probe(fake, tmp_path, payload)
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "malformed_payload"
E       AssertionError: assert 'timeout' == 'malformed_payload'
E         
E         - malformed_payload
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:423: AssertionError
________ test_grok_usage_probe_invalid_explicit_percent_is_malformed[0] ________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_invalid_2')
percent = '0'

    @pytest.mark.parametrize(
        "percent",
        [None, True, "0", -1.0],
    )
    def test_grok_usage_probe_invalid_explicit_percent_is_malformed(
        tmp_path: Path, percent: object
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "creditUsagePercent": percent,
                "isUnifiedBillingUser": True,
                "monthlyLimit": {"val": 1000},
                "used": {"val": 0},
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                },
            }
        }
        result, _, _ = _run_grok_probe(fake, tmp_path, payload)
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "malformed_payload"
E       AssertionError: assert 'timeout' == 'malformed_payload'
E         
E         - malformed_payload
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:423: AssertionError
______ test_grok_usage_probe_invalid_explicit_percent_is_malformed[-1.0] _______
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_invalid_3')
percent = -1.0

    @pytest.mark.parametrize(
        "percent",
        [None, True, "0", -1.0],
    )
    def test_grok_usage_probe_invalid_explicit_percent_is_malformed(
        tmp_path: Path, percent: object
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "creditUsagePercent": percent,
                "isUnifiedBillingUser": True,
                "monthlyLimit": {"val": 1000},
                "used": {"val": 0},
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                },
            }
        }
        result, _, _ = _run_grok_probe(fake, tmp_path, payload)
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "malformed_payload"
E       AssertionError: assert 'timeout' == 'malformed_payload'
E         
E         - malformed_payload
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:423: AssertionError
__________ test_grok_usage_probe_false_unified_marker_stays_malformed __________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_false_un0')

    def test_grok_usage_probe_false_unified_marker_stays_malformed(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "isUnifiedBillingUser": False,
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                },
            }
        }
        result, _, _ = _run_grok_probe(fake, tmp_path, payload)
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "malformed_payload"
E       AssertionError: assert 'timeout' == 'malformed_payload'
E         
E         - malformed_payload
E         + timeout

tests/llm_provider/test_grok_usage_probe.py:443: AssertionError
___________ test_grok_usage_probe_native_plan_label_beats_camel_case ___________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_native_p0')

    def test_grok_usage_probe_native_plan_label_beats_camel_case(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "subscription_tier": "SuperGrok Heavy",
            "subscriptionTier": "Ignored",
            "config": {
                "creditUsagePercent": 10.0,
                "subscriptionTier": "Also Ignored",
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                },
            },
        }
        result, _, _ = _run_grok_probe(fake, tmp_path, payload)
>       assert result["plan"] == "SuperGrok Heavy"
E       AssertionError: assert None == 'SuperGrok Heavy'

tests/llm_provider/test_grok_usage_probe.py:464: AssertionError
_____________ test_grok_usage_probe_over_100_percent_is_preserved ______________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_over_1000')

    def test_grok_usage_probe_over_100_percent_is_preserved(tmp_path: Path) -> None:
        fake = _make_fake_grok(tmp_path)
        payload = {
            "config": {
                "creditUsagePercent": 150.0,
                "currentPeriod": {
                    "type": "USAGE_PERIOD_TYPE_WEEKLY",
                    "start": "2027-01-15T00:00:00Z",
                    "end": "2027-01-22T00:00:00Z",
                },
            }
        }
        result, _, _ = _run_grok_probe(fake, tmp_path, payload)
>       assert result["windows"][0]["used_percent"] == pytest.approx(150.0)
               ^^^^^^^^^^^^^^^^^^^^
E       IndexError: list index out of range

tests/llm_provider/test_grok_usage_probe.py:507: IndexError
_______________ test_grok_usage_probe_reaps_descendant_processes _______________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw25/test_grok_usage_probe_reaps_de0')

    def test_grok_usage_probe_reaps_descendant_processes(tmp_path: Path) -> None:
        fake = _make_fake_grok(tmp_path)
        pidfile = tmp_path / "child.pid"
        env = {
            "SASE_FAKE_GROK_MODE": "descendants",
            "SASE_FAKE_GROK_CHILD_PID": str(pidfile),
        }
        now = time.time()
        context = default_probe_context(
            "grok", now=now, deadline_seconds=3.0, executable=str(fake)
        )
        probe_result = run_usage_probe(
            context,
            isolate=True,
            plugin_spec={"kind": "entry_point", "name": "grok"},
            now=now,
            env=env,
        )
        result = probe_result.observation
        assert result is not None
        assert result["outcome"] == "error"
        assert result["reason_code"] == "timeout"
        deadline = time.time() + 2.0
        pid_text = ""
        while time.time() < deadline:
            if pidfile.exists():
                pid_text = pidfile.read_text(encoding="utf-8").strip()
                if pid_text:
                    break
            time.sleep(0.05)  # sase-test-wait: pidfile from descendant grok child
>       assert pid_text
E       AssertionError: assert ''

tests/llm_provider/test_grok_usage_probe.py:658: AssertionError
__________ test_file_backed_home_path_hint_uses_filesystem_resolution __________
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_file_backed_home_path_hin0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f2c0ad38c20>

    async def test_file_backed_home_path_hint_uses_filesystem_resolution(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        home = tmp_path / "home"
        note_dir = tmp_path / "notes"
        artifact_context = make_artifact_context(tmp_path)
        checkout = artifact_context.repositories[0].checkout_paths[0]
        for directory in (home, checkout, note_dir):
            directory.mkdir(parents=True)
        home_config = home / ".ssh" / "config"
        home_config.parent.mkdir()
        home_config.write_text("Host home\n", encoding="utf-8")
        decoy = checkout / "~" / ".ssh" / "config"
        decoy.parent.mkdir(parents=True)
        decoy.write_text("Host decoy\n", encoding="utf-8")
        note = note_dir / "tailnet.md"
        note.write_text("Use `~/.ssh/config` for SSH config.\n", encoding="utf-8")
        monkeypatch.setenv("HOME", str(home))
        monkeypatch.setattr(
            "sase.pager.source_resolve.artifact_context_for_link_context",
            lambda _context: artifact_context,
        )
        document = document_from_paths(
            [note],
            cwd=note_dir,
            link_context=LinkResolutionContext(
                anchors=(LinkAnchor(directory=note_dir),),
                owner=ArtifactRefDocumentOwner(
                    repository="sase",
                    source_directory=str(checkout),
                    checkout_candidates=(checkout,),
                ),
            ),
        )
    
        app = SasePager(document)
        async with app.run_test(size=(120, 40)) as pilot:
            await settle(pilot)
            screen = pager_screen(app)
            assert screen.document is document
            label = label_for(screen, "~/.ssh/config")
            await press_hint(pilot, label.hint)
>           assert screen.document is not document
E           AssertionError: assert PagerDocument(sections=(PagerSection(identity='file:/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_fi...est-of-bryan/pytest-0/popen-gw14/test_file_backed_home_path_hin0/workspace'),), path_globs=None)), expand_fold_fn=None) is not PagerDocument(sections=(PagerSection(identity='file:/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_fi...est-of-bryan/pytest-0/popen-gw14/test_file_backed_home_path_hin0/workspace'),), path_globs=None)), expand_fold_fn=None)
E            +  where PagerDocument(sections=(PagerSection(identity='file:/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw14/test_fi...est-of-bryan/pytest-0/popen-gw14/test_file_backed_home_path_hin0/workspace'),), path_globs=None)), expand_fold_fn=None) = PagerScreen().document

tests/pager/test_rendered_link_contract.py:212: AssertionError
__________ test_streaming_transfer_succeeds_while_progress_continues ___________
[gw3] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_streaming_transfer_succee0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f41727d6a50>

    def test_streaming_transfer_succeeds_while_progress_continues(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        seen_args: list[list[str]] = []
        script = (
            "import sys, time\n"
            "for index in range(6):\n"
            "    sys.stderr.write(f'Counting objects: {index}\\r')\n"
            "    sys.stderr.flush()\n"
            "    time.sleep(0.05)\n"
            "sys.stdout.write('done')\n"
        )
    
        def command(args: list[str]) -> list[str]:
            seen_args.append(args)
            return [sys.executable, "-c", script]
    
        monkeypatch.setenv("SASE_SDD_GIT_NETWORK_TRANSFER_CEILING", "2")
        monkeypatch.setattr("sase.sdd._git_runner.sdd_git_command", command)
    
>       result = run_sdd_git(
            ["clone", "source", "target"],
            cwd=tmp_path,
            op="test.clone",
            timeout=0.15,
            check=True,
            capture_output=True,
            text=True,
        )

tests/sdd_store/test_sdd_git_streaming.py:80: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/sdd/_git_runner.py:52: in run_sdd_git
    return _run_streaming_sdd_git(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

args = ['clone', '--progress', 'source', 'target']

    def _run_streaming_sdd_git(
        args: list[str],
        *,
        cwd: Path,
        op: str,
        stall_timeout_seconds: float,
        check: bool,
        text: bool,
        env: Mapping[str, str] | None,
        always_log: bool,
        telemetry: Mapping[str, Any] | None,
        retryability_operation_kind: str | None,
        output_previews: bool,
    ) -> subprocess.CompletedProcess[Any]:
        """Run a long git transfer, aborting on idle progress rather than wall time."""
    
        cmd = sdd_git_command(args)
        start = time.perf_counter()
        start_monotonic = time.monotonic()
        last_progress = start_monotonic
        ceiling_seconds = _network_transfer_ceiling_timeout()
        stdout_chunks: list[bytes] = []
        stderr_chunks: list[bytes] = []
    
        process = subprocess.Popen(
            cmd,
            cwd=cwd,
            stdout=subprocess.PIPE,
            stderr=subprocess.PIPE,
            text=False,
            env=env,
            start_new_session=os.name == "posix",
        )
        completed = False
        termination_attempted = False
        try:
            with selectors.DefaultSelector() as selector:
                assert process.stdout is not None
                assert process.stderr is not None
                selector.register(process.stdout, selectors.EVENT_READ, stdout_chunks)
                selector.register(process.stderr, selectors.EVENT_READ, stderr_chunks)
    
                while selector.get_map():
                    now = time.monotonic()
                    stall_deadline = last_progress + stall_timeout_seconds
                    ceiling_deadline = start_monotonic + ceiling_seconds
                    next_deadline = min(stall_deadline, ceiling_deadline)
                    if now >= next_deadline:
                        if now >= ceiling_deadline:
                            reason = "ceiling"
                            message = (
                                f"git operation {op!r} exceeded streaming ceiling "
                                f"{format_seconds(ceiling_seconds)}s in {cwd}"
                            )
                        else:
                            reason = "stall"
                            message = (
                                f"git operation {op!r} stalled after "
                                f"{format_seconds(stall_timeout_seconds)}s without "
                                f"progress in {cwd}"
                            )
                        termination_attempted = True
                        stdout, stderr = _terminate_streaming_git(
                            process,
                            stdout_chunks=stdout_chunks,
                            stderr_chunks=stderr_chunks,
                        )
                        duration_ms = (time.perf_counter() - start) * 1000.0
                        _log_git_operation(
                            op=op,
                            cmd=cmd,
                            cwd=cwd,
                            status="timeout",
                            duration_ms=duration_ms,
                            timeout_seconds=stall_timeout_seconds,
                            returncode=process.returncode,
                            stdout=decode_stream(stdout, text=text),
                            stderr=decode_stream(stderr, text=text),
                            timeout_reason=reason,
                            telemetry=telemetry,
                            retryability_operation_kind=retryability_operation_kind,
                            output_previews=output_previews,
                        )
>                       raise SddGitCommandTimeout(message)
E                       sase.sdd._git_config.SddGitCommandTimeout: git operation 'test.clone' stalled after 0.15s without progress in /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw3/test_streaming_transfer_succee0

src/sase/sdd/_git_runner.py:218: SddGitCommandTimeout
_____ test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive ______
[gw11] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw11/test_auto_refresh_soak_keeps_e0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f22b4cf9940>
project_display_case = ProjectDisplayCase(project_key='gh_acme__widgets', project_label='widgets', patch_key='gh_acme__widgets_feature', patc...ayProjection(project_key='gh_acme__widgets', project_label='widgets'),), signature=(('gh_acme__widgets', 'widgets'),)))

    async def test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
        project_display_case: ProjectDisplayCase,
    ) -> None:
        stall_log = tmp_path / "tui_stalls.jsonl"
        perf_log = tmp_path / "tui_jk.jsonl"
        monkeypatch.setenv("SASE_TUI_STALL_PATH", str(stall_log))
        monkeypatch.setenv("SASE_TUI_PERF", "1")
        monkeypatch.setenv("SASE_TUI_PERF_PATH", str(perf_log))
        monkeypatch.setenv("SASE_TUI_HITCH_THRESHOLD_SECONDS", "0.5")
        monkeypatch.setenv("SASE_TUI_PUMP_HITCH_THRESHOLD_SECONDS", "0.5")
        monkeypatch.setenv("SASE_TUI_STALL_THRESHOLD_SECONDS", "1.0")
        monkeypatch.setenv("SASE_TUI_PUMP_STALL_THRESHOLD_SECONDS", "1.0")
        monkeypatch.setenv("SASE_TUI_STALL_POLL_INTERVAL", "0.02")
        monkeypatch.setenv("SASE_TUI_PUMP_STALL_POLL_INTERVAL", "0.02")
        monkeypatch.setattr(sp, "_REFRESH_INTERVAL_SECONDS", 0.2)
    
        calls: list[tuple[StatisticsView, StatsRange, str | None, str | None]] = []
        _patch_center(
            monkeypatch,
            calls,
            project_display_case=project_display_case,
        )
    
        async with AcePage() as page:
            _, pane = await _open_statistics(page)
            await asyncio.sleep(1.1)  # sase-test-wait: auto-refresh soak window
            # Soak for a fixed window, then wait on the observed refresh count
            # rather than assuming the window produced it. A loaded CI runner can
            # starve the 0.2s refresh timer enough that 1.1s of wall clock yields
            # only three refreshes, which is scheduling pressure and not the
            # unresponsiveness this test guards against.
            await page.wait_for(lambda _state: len(calls) >= 4, timeout=30.0)
            await page.wait_for(lambda _state: not pane._loading)
    
            assert len(calls) >= 4
            assert all(call[0] == "overview" for call in calls)
            assert pane._last_result is not None
            rendered = _render_plain(
                pane._overview_renderable(pane._last_result.views.overview)
            )
            assert project_display_case.project_label in rendered
            assert project_display_case.project_key not in rendered
    
            pane._set_view("projects")
            await page.wait_for(
                lambda _state: (
                    pane._view == "projects"
                    and pane._last_result is not None
                    and pane._last_result.project_stats is not None
                    and pane._code_complete
                ),
                timeout=30.0,
            )
            projects_calls = len(calls)
            await asyncio.sleep(1.1)  # sase-test-wait: projects auto-refresh soak window
            await page.wait_for(
                lambda _state: len(calls) >= projects_calls + 3, timeout=30.0
            )
            await page.wait_for(
                lambda _state: (
                    pane._last_result is not None
                    and pane._last_result.project_stats is not None
                    and pane._code_complete
                ),
                timeout=30.0,
            )
            assert pane._last_result is not None
            assert pane._last_result.project_stats is not None
            assert pane._code_complete is True
            assert all(call[0] == "projects" for call in calls[projects_calls:])
    
            samples: list[float] = []
            for _ in range(20):
                started = time.perf_counter()
                pane.action_cycle_group()
                samples.append((time.perf_counter() - started) * 1000.0)
            samples.sort()
            group_p95 = samples[max(0, int(round(0.95 * (len(samples) - 1))))]
>           assert group_p95 < 16.0
E           assert 84.16815600503469 < 16.0

tests/ace/tui/test_statistics_pane_loading.py:248: AssertionError
______________ test_pager_follows_bead_links_and_preserves_trail _______________
[gw10] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw10/test_pager_follows_bead_links_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc17348da20>

    async def test_pager_follows_bead_links_and_preserves_trail(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        first, second, third = _seed_beads(tmp_path, monkeypatch)
        body = f"typed @bead:{second.id}\nbare {second.id}\n"
        section = PagerSection(
            identity=f"bead:{first.id}",
            title=first.id,
            kind="bead",
            body=body,
            subject_ref=f"bead:{first.id}",
            link_anchors=(LinkAnchor(tmp_path),),
            origin=PagerOrigin.BEAD,
        )
        source = PagerDocument(
            sections=(section,),
            title=first.id,
            origin=PagerOrigin.BEAD,
        )
        app = SasePager(source)
    
        async with app.run_test(size=(100, 28)) as pilot:
            screen = app.screen
            assert isinstance(screen, PagerScreen)
            await pilot.pause()
    
            await pilot.press(_hint_for_target(screen, f"bead:{second.id}"))
            await pilot.pause(0.2)
            await pilot.pause(0.2)
    
>           assert screen.document.title == f"{second.id} · Pager second"
E           AssertionError: assert 'test_pager_f...ead_links_0-1' == 'test_pager_f... Pager second'
E             
E             - test_pager_follows_bead_links_0-2 · Pager second
E             ?                                 ^^^^^^^^^^^^^^^^
E             + test_pager_follows_bead_links_0-1
E             ?                                 ^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/pager/test_bead_live_links.py:172: AssertionError
________________ test_split_open_and_close_releases_both_panes _________________
[gw22] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    async def test_split_open_and_close_releases_both_panes() -> None:
        """A split opened and closed inside one push/pop cycle leaves nothing."""
        host = SasePager(long_document())
        async with host.run_test(size=_HOST_SIZE) as pilot:
            await pilot.pause()
            pushed = PagerScreen(host.document)
            await host.push_screen(pushed)
            await pilot.pause()
            await pilot.press("\\")
            await pilot.pause()
            await pilot.pause()
            assert len(pushed.views) == 2
            removed_ref = weakref.ref(pushed.views[0])
            survivor_ref = weakref.ref(pushed.views[1])
            await pilot.press("\\")
            await pilot.pause()
            await pilot.pause()
            assert len(pushed.views) == 1
            # The removed pane already left the theme signal on unmount: the
            # old watcher leak pinned every closed view from the app.
            subscriptions = host.theme_changed_signal._subscriptions  # noqa: SLF001
            assert removed_ref() not in subscriptions
            await host.pop_screen()
            del pushed
>           await _settle_released([removed_ref, survivor_ref], pilot)

tests/pager/test_view_leak.py:93: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/pager/test_view_leak.py:36: in _settle_released
    await wait_for(pilot, _released)
src/sase/ace/testing/wait.py:88: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function _settle_released.<locals>._released at 0x7f3cd7129430>

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
E               AssertionError: wait_for(_settle_released.<locals>._released) timed out after 5.0s waiting for it to return True

src/sase/ace/testing/wait.py:54: AssertionError
_______________ test_footprint_finder_filters_and_drills_to_area _______________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f76209cff50>

    async def test_footprint_finder_filters_and_drills_to_area(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        import sase.ace.tui.modals.statistics_footprint_finder_modal as finder_modal
    
        monkeypatch.setattr(
            finder_modal,
            "catalog_features",
            lambda: (
                finder_modal._FinderFeature(
                    "cli:bead.list", "bead list", "cli.bead", "command"
                ),
                finder_modal._FinderFeature(
                    "tui:statistics.cycle_range",
                    "Cycle Statistics range",
                    "tui.statistics",
                    "action",
                ),
            ),
        )
        calls: list[tuple[object, ...]] = []
        _patch_center(monkeypatch, calls)
    
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_statistics_footprint.py:530: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:355: in __aexit__
    await _drain_app_work(app)
src/sase/ace/testing/ace_page.py:214: in _drain_app_work
    raise worker_error
src/sase/ace/testing/ace_page.py:209: in _drain_app_work
    await _drain_textual_workers(app)
src/sase/ace/testing/ace_page.py:202: in _drain_textual_workers
    raise result
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Worker ERROR name='task' group='statistics-footprint-card' description='<function StatisticsPaneActionsFootprintMixin._start_footprint_card_load.<locals>.task at 0x7f75fe3a96f0>'>

    async def wait(self) -> ResultType:
        """Wait for the work to complete.
    
        Raises:
            WorkerFailed: If the Worker raised an exception.
            WorkerCancelled: If the Worker was cancelled before it completed.
    
        Returns:
            The return value of the work.
        """
        try:
            if active_worker.get() is self:
                raise DeadlockError(
                    "Can't call worker.wait from within the worker function!"
                )
        except LookupError:
            # Not in a worker
            pass
    
        if self.state == WorkerState.PENDING:
            raise WorkerError("Worker must be started before calling this method.")
        if self._task is not None:
            try:
                await self._task
            except asyncio.CancelledError as error:
                self.state = WorkerState.CANCELLED
                self._error = error
        if self.state == WorkerState.ERROR:
            assert self._error is not None
>           raise WorkerFailed(self._error)
E           textual.worker.WorkerFailed: Worker raised exception: ValueError('unknown feature cli:bead.list')

.venv/lib/python3.14/site-packages/textual/worker.py:452: WorkerFailed
---------------------------- Captured log teardown -----------------------------
ERROR    asyncio:base_events.py:1886 an error occurred during closing of asynchronous generator <async_generator object App.run_test at 0x7f7610907370>
asyncgen: <async_generator object App.run_test at 0x7f7610907370>
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/textual/app.py", line 1053, in _context
    yield
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/textual/app.py", line 2137, in run_test
    yield pilot
GeneratorExit

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/textual/app.py", line 2132, in run_test
    with app._context():
         ~~~~~~~~~~~~^^
  File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 162, in __exit__
    self.gen.throw(value)
    ~~~~~~~~~~~~~~^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/textual/app.py", line 1055, in _context
    active_message_pump.reset(message_pump_reset_token)
    ~~~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^
ValueError: <Token var=<ContextVar name='active_message_pump' at 0x7f762fa893a0> at 0x7f75fdb4b180> was created in a different Context
_______ test_sudo_answer_waits_for_concurrent_reclaimer_without_failure ________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw1/test_sudo_answer_waits_for_con0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f4c6d4d2040>

    def test_sudo_answer_waits_for_concurrent_reclaimer_without_failure(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setenv("SASE_HOME", str(tmp_path / "sase-home"))
        gate, envelope, record, artifacts_dir = _sudo_gate_with_turn(
            request_id="sudo-followup-race"
        )
        import sase.gate_turn.settlement as settlement_module
    
        monkeypatch.setattr(settlement_module, "FOLLOWUP_LOCK_TIMEOUT_SECONDS", 0.05)
        monkeypatch.setattr(
            settlement_module, "CREATOR_LIVE_FOLLOWUP_LOCK_TIMEOUT_SECONDS", 1.0
        )
        monkeypatch.setattr(
            "sase.notification_gates.executor.has_controlling_tty", lambda: True
        )
        monkeypatch.setattr(
            settlement_module, "hold_gate_turn_claim_for_settlement", lambda *a, **k: None
        )
        monkeypatch.setattr(
            settlement_module, "finalize_turn_workflow_state", lambda *_args: None
        )
        monkeypatch.setattr(
            settlement_module, "touch_turn_refresh_pulse", lambda *_args: None
        )
    
        answer_written = threading.Event()
        launch_started = threading.Event()
        release_launch = threading.Event()
        launch_calls: list[str] = []
        thread_errors: list[BaseException] = []
    
        def blocked_followup(
            called_dir: str,
            meta: dict[str, Any],
            **kwargs: Any,
        ) -> None:
            del called_dir, kwargs
            launch_calls.append("launched")
            meta["gate_followup_agent"] = "sudo-followup"
            meta["gate_followup_outcome"] = "launched"
            launch_started.set()
            timer = threading.Timer(0.15, release_launch.set)
            timer.start()
            release_launch.wait(timeout=2)
    
        monkeypatch.setattr(
            settlement_module, "launch_or_record_followup", blocked_followup
        )
        from sase.sudo import answer_ops
    
        real_execute = answer_ops.execute_gate_selection
    
        def execute_then_wait_for_reclaimer(*args: Any, **kwargs: Any) -> Any:
            result = real_execute(*args, **kwargs)
            answer_written.set()
            assert launch_started.wait(timeout=2)
            return result
    
        monkeypatch.setattr(
            answer_ops, "execute_gate_selection", execute_then_wait_for_reclaimer
        )
    
        def reclaim() -> None:
            try:
                assert answer_written.wait(timeout=2)
                settlement_module.settle_gate_turn(
                    record, gate_state="answered", reason="gate answered"
                )
            except BaseException as exc:
                thread_errors.append(exc)
    
        reclaim_thread = threading.Thread(target=reclaim)
        reclaim_thread.start()
        try:
>           payload = _apply_sudo_receipt(gate, envelope)
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_sudo_ledger_settlement.py:308: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/test_sudo_ledger_settlement.py:66: in _apply_sudo_receipt
    return apply_approved_receipt(
src/sase/sudo/answer_ops.py:126: in apply_approved_receipt
    execution = execute_gate_selection(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

args = (PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw1/test_sudo_answer_waits_for_con0/sase-home/interaction_requests/sudo/sudo-followup-race'), ['approve'])
kwargs = {'feedback': None, 'option_inputs': {'approve': {'command_ids': ['refresh'], 'receipt': {'diagnostic': None, 'entries'...82884b8af492e4b3db8bcd4ef59c4ccccb114670f79', 'outcome': 'completed', ...}}}, 'retry': None, 'source': 'sudo_cli', ...}
result = GateExecutionResult(response={'schema_version': 2, 'request_id': 'sudo-followup-race', 'kind': 'sudo', 'selected_optio...ack': None, 'source': 'sudo_cli', 'caller': 'human', 'responded_at_unix': 1794085929.2739546}, already_completed=False)
@py_assert1 = <bound method Event.wait of <threading.Event at 0x7f4c50ec8050: unset>>
@py_assert3 = 2, @py_assert5 = False
@py_format7 = 'assert False\n{False = wait\n{wait = <threading.Event at 0x7f4c50ec8050: unset>.wait\n}(timeout=2)\n}'

    def execute_then_wait_for_reclaimer(*args: Any, **kwargs: Any) -> Any:
        result = real_execute(*args, **kwargs)
        answer_written.set()
>       assert launch_started.wait(timeout=2)
E       assert False
E        +  where False = wait(timeout=2)
E        +    where wait = <threading.Event at 0x7f4c50ec8050: unset>.wait

tests/test_sudo_ledger_settlement.py:289: AssertionError
_________ test_blocked_render_is_bounded_and_leaves_the_request_queued _________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_blocked_render_is_bounded0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f75ffca3380>

    def test_blocked_render_is_bounded_and_leaves_the_request_queued(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        owner = AgentOwnerIdentity("alice", "athena")
        target, _remote = _configure_target(monkeypatch, tmp_path, owner)
        timings = []
        monkeypatch.setattr(publication_drain, "emit_drain_timing", timings.append)
    
        def blocked_render(*_args, **_kwargs):
            time.sleep(30)  # sase-test-wait: exceeds the drain timeout
            raise AssertionError("blocked render should have been interrupted")
    
        monkeypatch.setattr(publication_locked, "publish_agent_hood", blocked_render)
        monkeypatch.setattr(
            publication_drain,
            "_configured_publication_drain_timeout",
            lambda: 1.0,
        )
    
        started = time.perf_counter()
        outcome = publish_committed_agent_hood(
            "foo--code",
            "a" * 40,
            project="Project",
            git_runner=run_git,
        )
        elapsed = time.perf_counter() - started
    
>       assert elapsed < 5.0
E       assert 34.47510311700171 < 5.0

tests/agents_sync/test_commit_publication_bounded_drain.py:109: AssertionError
_____ test_manifest_timeout_cleans_regenerable_paths_and_preserves_objects _____
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_manifest_timeout_cleans_r0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f75fe4217f0>

    def test_manifest_timeout_cleans_regenerable_paths_and_preserves_objects(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        owner = AgentOwnerIdentity("alice", "athena")
        target, _remote = _configure_target(monkeypatch, tmp_path, owner)
        timings = []
        monkeypatch.setattr(publication_drain, "emit_drain_timing", timings.append)
    
        def publish_with_scratch(_target, repo, agent, **kwargs):
            (repo / "prompts").mkdir(exist_ok=True)
            (repo / "prompts" / "scratch.md").write_text("regenerable prompt\n")
            (repo / "artifacts").mkdir(exist_ok=True)
            (repo / "artifacts" / "scratch.bin").write_bytes(b"regenerable")
            object_path = repo / "files" / "objects" / "sha256" / "aa" / "pending"
            object_path.parent.mkdir(parents=True, exist_ok=True)
            object_path.write_bytes(b"append-only object")
            return _publish_readme(owner)(_target, repo, agent, **kwargs)
    
        def blocked_manifest(*_args, **_kwargs):
            time.sleep(30)  # sase-test-wait: exceeds the drain timeout
    
        monkeypatch.setattr(publication_locked, "publish_agent_hood", publish_with_scratch)
        monkeypatch.setattr(
            transaction_steps,
            "read_owner_manifest",
            blocked_manifest,
        )
        monkeypatch.setattr(
            publication_drain,
            "_configured_publication_drain_timeout",
            lambda: 5.0,
        )
    
        outcome = publish_committed_agent_hood(
            "foo--code",
            "a" * 40,
            project="Project",
            git_runner=run_git,
        )
    
        assert outcome.queued and not outcome.published
        assert outcome.error is not None and "did not complete within" in outcome.error
        assert timings and timings[-1].alarm_fired
        assert timings[-1].alarm_stage == "manifest_verify"
>       assert not (target.sidecar_path / "prompts" / "scratch.md").exists()
E       AssertionError: assert not True
E        +  where True = exists()
E        +    where exists = ((PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_manifest_timeout_cleans_r0/sidecar') / 'prompts') / 'scratch.md').exists
E        +      where PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_manifest_timeout_cleans_r0/sidecar') = ProjectTarget(project_key='proj', project='Project', primary_checkout=PosixPath('/var/tmp/sase-02a72d87/pytest-of-brya.../sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_manifest_timeout_cleans_r0/remote.git', primary_repo_name=None).sidecar_path

tests/agents_sync/test_commit_publication_bounded_drain.py:172: AssertionError
________ test_after_a_blocked_render_a_later_drain_retries_and_succeeds ________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_after_a_blocked_render_a_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f75fe421860>

    def test_after_a_blocked_render_a_later_drain_retries_and_succeeds(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        owner = AgentOwnerIdentity("alice", "athena")
        _configure_target(monkeypatch, tmp_path, owner)
    
        def blocked_render(*_args, **_kwargs):
            time.sleep(30)  # sase-test-wait: exceeds the drain timeout
    
        monkeypatch.setattr(publication_locked, "publish_agent_hood", blocked_render)
        monkeypatch.setattr(
            publication_drain,
            "_configured_publication_drain_timeout",
            lambda: 1.0,
        )
    
        first = publish_committed_agent_hood(
            "foo--code",
            "a" * 40,
            project="Project",
            git_runner=run_git,
        )
        assert first.queued and not first.published
        assert len(list_agent_publications("proj")) == 1
    
        monkeypatch.setattr(
            publication_locked, "publish_agent_hood", _publish_readme(owner)
        )
        monkeypatch.setattr(
            publication_drain,
            "_configured_publication_drain_timeout",
            lambda: 5.0,
        )
        monkeypatch.setattr(
            "sase.agents_sync.publication_completion.publication_request_completion",
            fulfilled_completion,
        )
        monkeypatch.setattr(
            "sase.agents_sync.prompt_archive.deferred.restore_deferred_prompt_archives",
            lambda *_args, **_kwargs: {},
        )
    
        second = publish_committed_agent_hood(
            "foo--code",
            "a" * 40,
            project="Project",
            git_runner=run_git,
        )
>       assert second.published and not second.error
E       AssertionError: assert (False)
E        +  where False = CommitPublicationOutcome(published=False, queued=False, drained=0, quarantined=0, retired=0, skip_reason=None, error='...did not complete within 5s', failure_scope='repository', parked_keys=(), newly_parked_keys=(), failure_stage='cleanup').published

tests/agents_sync/test_commit_publication_bounded_drain.py:287: AssertionError
________ test_policy_lookup_failure_preserves_drain_timeout_attribution ________
[gw8] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw8/test_policy_lookup_failure_pre0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fa9732ed710>

    def test_policy_lookup_failure_preserves_drain_timeout_attribution(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        owner = AgentOwnerIdentity("alice", "athena")
        target, _remote = _configure_target(monkeypatch, tmp_path, owner)
        timings: list = []
        monkeypatch.setattr(publication_drain, "emit_drain_timing", timings.append)
    
        def blocked_render(*_args: Any, **_kwargs: Any):
            time.sleep(30)  # sase-test-wait: exceeds the drain timeout
    
        monkeypatch.setattr(publication_locked, "publish_agent_hood", blocked_render)
        monkeypatch.setattr(
            publication_drain,
            "_configured_publication_drain_timeout",
            lambda: 1.0,
        )
        lookups = _raise_missing(monkeypatch)
    
        started = time.perf_counter()
        outcome = publish_committed_agent_hood(
            "foo--code",
            "a" * 40,
            project="Project",
            git_runner=run_git,
        )
        elapsed = time.perf_counter() - started
    
>       assert elapsed < 5.0
E       assert 34.72467451499688 < 5.0

tests/agents_sync/test_publication_cleanup_policy.py:254: AssertionError
_____________ test_blocked_render_with_young_index_lock_is_bounded _____________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_blocked_render_with_young0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f75fe39ecf0>

    def test_blocked_render_with_young_index_lock_is_bounded(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """Young owner-free index.lock during a blocked render stays under 5s.
    
        Fault-injects the post-alarm cleanup contention from the sase-xo probe:
        the blocked renderer creates a fresh sidecar ``.git/index.lock`` just
        before sleeping, so exception cleanup must recover through git-lock
        budgets instead of waiting out the 15s stale age.
        """
        owner = AgentOwnerIdentity("alice", "athena")
        target, _remote = _configure_target(monkeypatch, tmp_path, owner)
        timings: list = []
        monkeypatch.setattr(publication_drain, "emit_drain_timing", timings.append)
    
        sidecar = target.sidecar_path
    
        def blocked_render_with_lock(*_args, **_kwargs):
            git_dir = sidecar / ".git"
            try:
                git_dir.mkdir(parents=True, exist_ok=True)
                (git_dir / "index.lock").write_bytes(b"test contention")
            except OSError:
                pass
            time.sleep(30)  # sase-test-wait: exceeds the drain timeout
            raise AssertionError("blocked render should have been interrupted")
    
        monkeypatch.setattr(
            publication_locked, "publish_agent_hood", blocked_render_with_lock
        )
        monkeypatch.setattr(
            publication_drain,
            "_configured_publication_drain_timeout",
            lambda: 1.0,
        )
    
        started = time.perf_counter()
        outcome = publish_committed_agent_hood(
            "foo--code",
            "a" * 40,
            project="Project",
            git_runner=run_git,
        )
        elapsed = time.perf_counter() - started
    
>       assert elapsed < 5.0, f"contention cleanup overran: {elapsed:.2f}s"
E       AssertionError: contention cleanup overran: 34.38s
E       assert 34.38161028600007 < 5.0

tests/agents_sync/test_commit_publication_bounded_drain.py:353: AssertionError
_____________________ test_descendant_processes_are_reaped _____________________
[gw12] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8445db3e00>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw12/test_descendant_processes_are_0')

    def test_descendant_processes_are_reaped(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path
    ) -> None:
        pidfile = tmp_path / "child.pid"
        monkeypatch.setenv("SASE_CODEX_APP_SERVER_PIDFILE", str(pidfile))
        context = _context(
            mode="descendants", monkeypatch=monkeypatch, deadline_seconds=1.5
        )
        observation = collect_codex_usage(context)
        assert observation["outcome"] == "error"
        assert observation["reason_code"] == "timeout"
>       child_pid = int(pidfile.read_text(encoding="utf-8"))
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/llm_provider/test_codex_usage_probe.py:325: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pathlib/__init__.py:787: in read_text
    with self.open(mode='r', encoding=encoding, errors=errors, newline=newline) as f:
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw12/test_descendant_processes_are_0/child.pid')
mode = 'r', buffering = -1, encoding = 'utf-8', errors = None, newline = None

    def open(self, mode='r', buffering=-1, encoding=None,
             errors=None, newline=None):
        """
        Open the file pointed to by this path and return a file object, as
        the built-in open() function does.
        """
        if "b" not in mode:
            encoding = io.text_encoding(encoding)
>       return io.open(self, mode, buffering, encoding, errors, newline)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       FileNotFoundError: [Errno 2] No such file or directory: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw12/test_descendant_processes_are_0/child.pid'

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pathlib/__init__.py:771: FileNotFoundError
_________ test_run_supervisor_kills_the_whole_process_group_on_timeout _________
[gw16] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_kills_the_0/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000'

    def _run_supervisor_subprocess(
        artifacts_dir: str,
        *,
        overrides: Mapping[str, float] | None = None,
        liveness_timeout: float = _NO_HANG_TIMEOUT,
    ) -> subprocess.CompletedProcess[str]:
        if overrides is None:
            argv = [
                sys.executable,
                "-m",
                "sase.monitor.supervise",
                "--artifacts-dir",
                artifacts_dir,
            ]
        else:
            argv = [
                sys.executable,
                "-c",
                _SUPERVISOR_OVERRIDE_DRIVER,
                artifacts_dir,
                json.dumps(overrides),
            ]
        try:
>           completed = subprocess.run(
                argv,
                env=os.environ.copy(),
                capture_output=True,
                text=True,
                timeout=liveness_timeout,
                check=False,
            )

tests/monitor/_supervise.py:159: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:557: in run
    stdout, stderr = process.communicate(input, timeout=timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1221: in communicate
    stdout, stderr = self._communicate(input, endtime, timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:2154: in _communicate
    self._check_timeout(endtime, orig_timeout, stdout, stderr)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Popen: returncode: -9 args: ['/home/bryan/.local/state/sase/workspaces/sase...>
endtime = 36948.878619822, orig_timeout = 15.0, stdout_seq = [], stderr_seq = []
skip_check_and_raise = False

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
E           subprocess.TimeoutExpired: Command '['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python', '-m', 'sase.monitor.supervise', '--artifacts-dir', '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_kills_the_0/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000']' timed out after 15.0 seconds

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1268: TimeoutExpired

During handling of the above exception, another exception occurred:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_kills_the_0')

    def test_run_supervisor_kills_the_whole_process_group_on_timeout(
        tmp_path: Path,
    ) -> None:
        pidfile = tmp_path / "grandchild.pid"
        command = f"sh -c 'sleep 30 & echo $! > {pidfile}; wait'"
        artifacts_dir, _ = _make_member(tmp_path, command=command, timeout_seconds=0.3)
    
>       completed = _run_supervisor_subprocess(artifacts_dir)
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/monitor/test_monitor_supervise_timeout.py:39: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_kills_the_0/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000'

    def _run_supervisor_subprocess(
        artifacts_dir: str,
        *,
        overrides: Mapping[str, float] | None = None,
        liveness_timeout: float = _NO_HANG_TIMEOUT,
    ) -> subprocess.CompletedProcess[str]:
        if overrides is None:
            argv = [
                sys.executable,
                "-m",
                "sase.monitor.supervise",
                "--artifacts-dir",
                artifacts_dir,
            ]
        else:
            argv = [
                sys.executable,
                "-c",
                _SUPERVISOR_OVERRIDE_DRIVER,
                artifacts_dir,
                json.dumps(overrides),
            ]
        try:
            completed = subprocess.run(
                argv,
                env=os.environ.copy(),
                capture_output=True,
                text=True,
                timeout=liveness_timeout,
                check=False,
            )
        except subprocess.TimeoutExpired as exc:
>           pytest.fail(
                f"supervisor subprocess did not exit within {liveness_timeout:g}s; "
                f"stdout={exc.stdout!r}; stderr={exc.stderr!r}"
            )
E           Failed: supervisor subprocess did not exit within 15s; stdout=None; stderr=None

tests/monitor/_supervise.py:168: Failed
_______________ test_run_supervisor_times_out_continuous_output ________________
[gw16] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_times_out_0/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000'

    def _run_supervisor_subprocess(
        artifacts_dir: str,
        *,
        overrides: Mapping[str, float] | None = None,
        liveness_timeout: float = _NO_HANG_TIMEOUT,
    ) -> subprocess.CompletedProcess[str]:
        if overrides is None:
            argv = [
                sys.executable,
                "-m",
                "sase.monitor.supervise",
                "--artifacts-dir",
                artifacts_dir,
            ]
        else:
            argv = [
                sys.executable,
                "-c",
                _SUPERVISOR_OVERRIDE_DRIVER,
                artifacts_dir,
                json.dumps(overrides),
            ]
        try:
>           completed = subprocess.run(
                argv,
                env=os.environ.copy(),
                capture_output=True,
                text=True,
                timeout=liveness_timeout,
                check=False,
            )

tests/monitor/_supervise.py:159: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:557: in run
    stdout, stderr = process.communicate(input, timeout=timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1221: in communicate
    stdout, stderr = self._communicate(input, endtime, timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:2154: in _communicate
    self._check_timeout(endtime, orig_timeout, stdout, stderr)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Popen: returncode: -9 args: ['/home/bryan/.local/state/sase/workspaces/sase...>
endtime = 36968.896092578, orig_timeout = 15.0, stdout_seq = [], stderr_seq = []
skip_check_and_raise = False

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
E           subprocess.TimeoutExpired: Command '['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python', '-m', 'sase.monitor.supervise', '--artifacts-dir', '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_times_out_0/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000']' timed out after 15.0 seconds

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1268: TimeoutExpired

During handling of the above exception, another exception occurred:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_times_out_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6434822c80>

    def test_run_supervisor_times_out_continuous_output(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setenv("SASE_MONITOR_LOG_MAX_BYTES", "4096")
        artifacts_dir, _ = _make_member(
            tmp_path,
            command="sh -c 'while :; do echo chatty; done'",
            timeout_seconds=0.2,
        )
    
>       completed = _run_supervisor_subprocess(artifacts_dir)
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/monitor/test_monitor_supervise_timeout.py:60: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_times_out_0/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000'

    def _run_supervisor_subprocess(
        artifacts_dir: str,
        *,
        overrides: Mapping[str, float] | None = None,
        liveness_timeout: float = _NO_HANG_TIMEOUT,
    ) -> subprocess.CompletedProcess[str]:
        if overrides is None:
            argv = [
                sys.executable,
                "-m",
                "sase.monitor.supervise",
                "--artifacts-dir",
                artifacts_dir,
            ]
        else:
            argv = [
                sys.executable,
                "-c",
                _SUPERVISOR_OVERRIDE_DRIVER,
                artifacts_dir,
                json.dumps(overrides),
            ]
        try:
            completed = subprocess.run(
                argv,
                env=os.environ.copy(),
                capture_output=True,
                text=True,
                timeout=liveness_timeout,
                check=False,
            )
        except subprocess.TimeoutExpired as exc:
>           pytest.fail(
                f"supervisor subprocess did not exit within {liveness_timeout:g}s; "
                f"stdout={exc.stdout!r}; stderr={exc.stderr!r}"
            )
E           Failed: supervisor subprocess did not exit within 15s; stdout=None; stderr=None

tests/monitor/_supervise.py:168: Failed
_______________ test_run_supervisor_times_out_after_partial_line _______________
[gw16] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_times_out_1/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000'

    def _run_supervisor_subprocess(
        artifacts_dir: str,
        *,
        overrides: Mapping[str, float] | None = None,
        liveness_timeout: float = _NO_HANG_TIMEOUT,
    ) -> subprocess.CompletedProcess[str]:
        if overrides is None:
            argv = [
                sys.executable,
                "-m",
                "sase.monitor.supervise",
                "--artifacts-dir",
                artifacts_dir,
            ]
        else:
            argv = [
                sys.executable,
                "-c",
                _SUPERVISOR_OVERRIDE_DRIVER,
                artifacts_dir,
                json.dumps(overrides),
            ]
        try:
>           completed = subprocess.run(
                argv,
                env=os.environ.copy(),
                capture_output=True,
                text=True,
                timeout=liveness_timeout,
                check=False,
            )

tests/monitor/_supervise.py:159: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:557: in run
    stdout, stderr = process.communicate(input, timeout=timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1221: in communicate
    stdout, stderr = self._communicate(input, endtime, timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:2154: in _communicate
    self._check_timeout(endtime, orig_timeout, stdout, stderr)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Popen: returncode: -9 args: ['/home/bryan/.local/state/sase/workspaces/sase...>
endtime = 36985.048409562, orig_timeout = 15.0, stdout_seq = [], stderr_seq = []
skip_check_and_raise = False

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
E           subprocess.TimeoutExpired: Command '['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python', '-m', 'sase.monitor.supervise', '--artifacts-dir', '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_times_out_1/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000']' timed out after 15.0 seconds

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1268: TimeoutExpired

During handling of the above exception, another exception occurred:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_times_out_1')

    def test_run_supervisor_times_out_after_partial_line(tmp_path: Path) -> None:
        artifacts_dir, _ = _make_member(
            tmp_path,
            command="sh -c 'printf partial; sleep 30'",
            # Long enough for spawn+printf under load; the child still sleeps 30s
            # so this remains a timeout, not a completion.
            timeout_seconds=3.0,
        )
    
>       completed = _run_supervisor_subprocess(artifacts_dir)
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/monitor/test_monitor_supervise_timeout.py:77: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_times_out_1/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000'

    def _run_supervisor_subprocess(
        artifacts_dir: str,
        *,
        overrides: Mapping[str, float] | None = None,
        liveness_timeout: float = _NO_HANG_TIMEOUT,
    ) -> subprocess.CompletedProcess[str]:
        if overrides is None:
            argv = [
                sys.executable,
                "-m",
                "sase.monitor.supervise",
                "--artifacts-dir",
                artifacts_dir,
            ]
        else:
            argv = [
                sys.executable,
                "-c",
                _SUPERVISOR_OVERRIDE_DRIVER,
                artifacts_dir,
                json.dumps(overrides),
            ]
        try:
            completed = subprocess.run(
                argv,
                env=os.environ.copy(),
                capture_output=True,
                text=True,
                timeout=liveness_timeout,
                check=False,
            )
        except subprocess.TimeoutExpired as exc:
>           pytest.fail(
                f"supervisor subprocess did not exit within {liveness_timeout:g}s; "
                f"stdout={exc.stdout!r}; stderr={exc.stderr!r}"
            )
E           Failed: supervisor subprocess did not exit within 15s; stdout=None; stderr=None

tests/monitor/_supervise.py:168: Failed
_________ test_run_supervisor_chatty_command_does_not_hit_idle_timeout _________
[gw16] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_chatty_com0')

    def test_run_supervisor_chatty_command_does_not_hit_idle_timeout(
        tmp_path: Path,
    ) -> None:
        command = (
            f'{shlex.quote(sys.executable)} -u -c "import sys, time; '
            "[(sys.stdout.write('tick\\\\n'), sys.stdout.flush(), time.sleep(0.05)) "
            'for _ in range(4)]"'
        )
        artifacts_dir, _ = _make_member(
            tmp_path,
            command=command,
            timeout_seconds=5.0,
            idle_timeout_seconds=0.2,
        )
    
        exit_status = run_supervisor(artifacts_dir)
    
>       assert exit_status == 0
E       assert 1 == 0

tests/monitor/test_monitor_supervise_timeout.py:174: AssertionError
___________ test_run_supervisor_escalates_term_ignoring_chatty_child ___________
[gw16] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_escalates_0/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000'

    def _run_supervisor_subprocess(
        artifacts_dir: str,
        *,
        overrides: Mapping[str, float] | None = None,
        liveness_timeout: float = _NO_HANG_TIMEOUT,
    ) -> subprocess.CompletedProcess[str]:
        if overrides is None:
            argv = [
                sys.executable,
                "-m",
                "sase.monitor.supervise",
                "--artifacts-dir",
                artifacts_dir,
            ]
        else:
            argv = [
                sys.executable,
                "-c",
                _SUPERVISOR_OVERRIDE_DRIVER,
                artifacts_dir,
                json.dumps(overrides),
            ]
        try:
>           completed = subprocess.run(
                argv,
                env=os.environ.copy(),
                capture_output=True,
                text=True,
                timeout=liveness_timeout,
                check=False,
            )

tests/monitor/_supervise.py:159: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:557: in run
    stdout, stderr = process.communicate(input, timeout=timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1221: in communicate
    stdout, stderr = self._communicate(input, endtime, timeout)
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:2154: in _communicate
    self._check_timeout(endtime, orig_timeout, stdout, stderr)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Popen: returncode: -9 args: ['/home/bryan/.local/state/sase/workspaces/sase...>
endtime = 37050.623987298, orig_timeout = 15.0, stdout_seq = [], stderr_seq = []
skip_check_and_raise = False

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
E           subprocess.TimeoutExpired: Command '['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python', '-c', 'import json\nimport sys\n\ntry:\n    import sase.monitor.supervise as supervise\n\n    for name, value in json.loads(sys.argv[2]).items():\n        getattr(supervise, name)  # a renamed constant must not be skipped\n        setattr(supervise, name, value)\nexcept BaseException as exc:  # noqa: BLE001 - reported through the exit code\n    print(f"supervisor driver setup failed: {exc!r}", file=sys.stderr)\n    raise SystemExit(91) from None\n\nraise SystemExit(supervise.run_supervisor(sys.argv[1]))\n', '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_escalates_0/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000', '{"_KILL_GRACE_SECONDS": 0.2}']' timed out after 15.0 seconds

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1268: TimeoutExpired

During handling of the above exception, another exception occurred:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_escalates_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f644d874de0>

    def test_run_supervisor_escalates_term_ignoring_chatty_child(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        monkeypatch.setenv("SASE_MONITOR_LOG_MAX_BYTES", "4096")
        artifacts_dir, _ = _make_member(
            tmp_path,
            command="sh -c 'trap \"\" TERM; while :; do echo stubborn; done'",
            timeout_seconds=0.2,
        )
    
>       completed = _run_supervisor_subprocess(
            artifacts_dir, overrides={"_KILL_GRACE_SECONDS": 0.2}
        )

tests/monitor/test_monitor_supervise_timeout.py:223: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

artifacts_dir = '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw16/test_run_supervisor_escalates_0/.sase/projects/proj/artifacts/ace-run/202608/12/20260812120000'

    def _run_supervisor_subprocess(
        artifacts_dir: str,
        *,
        overrides: Mapping[str, float] | None = None,
        liveness_timeout: float = _NO_HANG_TIMEOUT,
    ) -> subprocess.CompletedProcess[str]:
        if overrides is None:
            argv = [
                sys.executable,
                "-m",
                "sase.monitor.supervise",
                "--artifacts-dir",
                artifacts_dir,
            ]
        else:
            argv = [
                sys.executable,
                "-c",
                _SUPERVISOR_OVERRIDE_DRIVER,
                artifacts_dir,
                json.dumps(overrides),
            ]
        try:
            completed = subprocess.run(
                argv,
                env=os.environ.copy(),
                capture_output=True,
                text=True,
                timeout=liveness_timeout,
                check=False,
            )
        except subprocess.TimeoutExpired as exc:
>           pytest.fail(
                f"supervisor subprocess did not exit within {liveness_timeout:g}s; "
                f"stdout={exc.stdout!r}; stderr={exc.stderr!r}"
            )
E           Failed: supervisor subprocess did not exit within 15s; stdout=None; stderr=None

tests/monitor/_supervise.py:168: Failed
____________ test_muse_stream_framing_under_provider_timer_in_a_pty ____________
[gw19] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_muse_stream_framing_under_provider_timer_in_a_pty() -> None:
        """Exercise the actual Rich Live/FileProxy path used by provider_timer."""
        master_fd, slave_fd = pty.openpty()
        script = (
            "import time\n"
            "from sase.output import provider_timer\n"
            "from sase.llm_provider._subprocess_artifacts import append_stream_delta\n"
            "with provider_timer('Waiting for test provider'):\n"
            "    append_stream_delta('inline `co', False, None, None, new_chunk=True)\n"
            "    time.sleep(0.65)\n"
            "    append_stream_delta('de` stays\\nfinal fragment', False, None, None, new_chunk=False)\n"
            "    time.sleep(0.1)\n"
            "    print(flush=True)\n"
        )
        process = subprocess.Popen(
            [sys.executable, "-c", script],
            stdin=subprocess.DEVNULL,
            stdout=slave_fd,
            stderr=slave_fd,
            close_fds=True,
        )
        os.close(slave_fd)
        output = bytearray()
        deadline = time.monotonic() + 5
        try:
            while process.poll() is None or select.select([master_fd], [], [], 0)[0]:
                remaining = deadline - time.monotonic()
>               assert remaining > 0, "provider_timer PTY probe exceeded five seconds"
E               AssertionError: provider_timer PTY probe exceeded five seconds
E               assert -9.884199971565977e-05 > 0

tests/llm_provider/test_muse_provider_stream.py:288: AssertionError
______________________ test_every_command_spec_has_an_id _______________________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

by_id = {'auto:axe.agent_waits': {'area': 'automation', 'id': 'auto:axe.agent_waits', 'kind': 'auto', 'label': 'Resolve agent ...state_refresh', 'kind': 'auto', 'label': 'Converge already-published agent runs to verified terminal state', ...}, ...}

    def test_every_command_spec_has_an_id(
        by_id: dict[str, dict[str, Any]],
    ) -> None:
        from sase.ace.tui.commands.catalog import build_command_catalog
        from sase.ace.tui.keymaps.registry import load_keymap_registry
    
        registry = load_keymap_registry(load_bundled_config()["ace"])
        specs = [
            spec
            for spec in build_command_catalog(registry)
            if not spec.id.startswith("custom.")
        ]
        assert specs
        for spec in specs:
            feature_id = f"tui:{ids.sanitize(spec.id)}"
>           assert feature_id in by_id or feature_id in ids.NAVIGATION_ACTIONS, spec.id
E           AssertionError: artifacts.ref:plan
E           assert ('tui:artifacts.ref_plan' in {'auto:axe.agent_waits': {'area': 'automation', 'id': 'auto:axe.agent_waits', 'kind': 'auto', 'label': 'Resolve agent ...state_refresh', 'kind': 'auto', 'label': 'Converge already-published agent runs to verified terminal state', ...}, ...} or 'tui:artifacts.ref_plan' in frozenset({'tui:app.agents_next', 'tui:app.agents_prev', 'tui:app.beads_next', 'tui:app.beads_prev', 'tui:app.files_next', 'tui:app.files_next_version', ...}))
E            +  where frozenset({'tui:app.agents_next', 'tui:app.agents_prev', 'tui:app.beads_next', 'tui:app.beads_prev', 'tui:app.files_next', 'tui:app.files_next_version', ...}) = ids.NAVIGATION_ACTIONS

tests/footprint/test_catalog.py:136: AssertionError
__________________ test_agy_usage_probe_collects_four_windows __________________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_collects_0')

    def test_agy_usage_probe_collects_four_windows(tmp_path: Path) -> None:
        fake = _make_fake_agy(tmp_path)
        result, entries, _ = _run_agy_probe(fake, tmp_path)
>       assert result["outcome"] == "ok"
E       AssertionError: assert 'error' == 'ok'
E         
E         - ok
E         + error

tests/llm_provider/test_agy_usage_probe.py:205: AssertionError
_____________ test_agy_usage_probe_old_version_never_spawns_usage ______________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_old_versi0')

    def test_agy_usage_probe_old_version_never_spawns_usage(tmp_path: Path) -> None:
        fake = _make_fake_agy(tmp_path)
        result, entries, _ = _run_agy_probe(fake, tmp_path, version="1.0.10")
>       assert result["outcome"] == "unsupported"
E       AssertionError: assert 'error' == 'unsupported'
E         
E         - unsupported
E         + error

tests/llm_provider/test_agy_usage_probe.py:266: AssertionError
_________ test_agy_usage_probe_unparseable_version_never_spawns_usage __________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_unparseab0')

    def test_agy_usage_probe_unparseable_version_never_spawns_usage(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_agy(tmp_path)
        result, entries, _ = _run_agy_probe(fake, tmp_path, version="banana")
>       assert result["outcome"] == "unsupported"
E       AssertionError: assert 'error' == 'unsupported'
E         
E         - unsupported
E         + error

tests/llm_provider/test_agy_usage_probe.py:276: AssertionError
___________ test_agy_usage_probe_failed_version_probe_is_unsupported ___________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_failed_ve0')

    def test_agy_usage_probe_failed_version_probe_is_unsupported(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_agy(tmp_path)
        result, _, _ = _run_agy_probe(fake, tmp_path, version_exit="1")
>       assert result["outcome"] == "unsupported"
E       AssertionError: assert 'error' == 'unsupported'
E         
E         - unsupported
E         + error

tests/llm_provider/test_agy_usage_probe.py:286: AssertionError
_____________ test_agy_usage_probe_auth_prompt_is_logged_out_fast ______________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_auth_prom0')

    def test_agy_usage_probe_auth_prompt_is_logged_out_fast(tmp_path: Path) -> None:
        fake = _make_fake_agy(tmp_path)
        result, _, elapsed = _run_agy_probe(fake, tmp_path, mode="auth_prompt")
>       assert result["outcome"] == "unauthenticated"
E       AssertionError: assert 'error' == 'unauthenticated'
E         
E         - unauthenticated
E         + error

tests/llm_provider/test_agy_usage_probe.py:293: AssertionError
_____________ test_agy_usage_probe_hang_is_timeout_and_reaps_child _____________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_hang_is_t0')

    def test_agy_usage_probe_hang_is_timeout_and_reaps_child(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_agy(tmp_path)
        result, _, _ = _run_agy_probe(fake, tmp_path, mode="hang", deadline_seconds=3.0)
        assert result["outcome"] == "error"
        assert result["reason_code"] == "timeout"
>       pid = int((tmp_path / "agy.pid").read_text(encoding="utf-8").strip())
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/llm_provider/test_agy_usage_probe.py:308: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pathlib/__init__.py:787: in read_text
    with self.open(mode='r', encoding=encoding, errors=errors, newline=newline) as f:
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_hang_is_t0/agy.pid')
mode = 'r', buffering = -1, encoding = 'utf-8', errors = None, newline = None

    def open(self, mode='r', buffering=-1, encoding=None,
             errors=None, newline=None):
        """
        Open the file pointed to by this path and return a file object, as
        the built-in open() function does.
        """
        if "b" not in mode:
            encoding = io.text_encoding(encoding)
>       return io.open(self, mode, buffering, encoding, errors, newline)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       FileNotFoundError: [Errno 2] No such file or directory: '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_hang_is_t0/agy.pid'

../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pathlib/__init__.py:771: FileNotFoundError
_____________ test_agy_usage_probe_malformed_stdout_is_parse_error _____________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_malformed0')

    def test_agy_usage_probe_malformed_stdout_is_parse_error(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_agy(tmp_path)
        result, _, _ = _run_agy_probe(fake, tmp_path, mode="malformed")
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "parse_error"
E       AssertionError: assert 'timeout' == 'parse_error'
E         
E         - parse_error
E         + timeout

tests/llm_provider/test_agy_usage_probe.py:396: AssertionError
______________ test_agy_usage_probe_omitted_zero_row_is_exhausted ______________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_omitted_z0')

    def test_agy_usage_probe_omitted_zero_row_is_exhausted(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_agy(tmp_path)
        result, _, _ = _run_agy_probe(fake, tmp_path, mode="omitted_zero")
>       assert result["outcome"] == "ok"
E       AssertionError: assert 'error' == 'ok'
E         
E         - ok
E         + error

tests/llm_provider/test_agy_usage_probe.py:404: AssertionError
________________ test_agy_usage_probe_turn_ran_is_vendor_drift _________________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_turn_ran_0')

    def test_agy_usage_probe_turn_ran_is_vendor_drift(tmp_path: Path) -> None:
        fake = _make_fake_agy(tmp_path)
        result, _, _ = _run_agy_probe(fake, tmp_path, mode="turn_ran")
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "vendor_drift"
E       AssertionError: assert 'timeout' == 'vendor_drift'
E         
E         - vendor_drift
E         + timeout

tests/llm_provider/test_agy_usage_probe.py:413: AssertionError
___________ test_agy_usage_probe_missing_executable_is_not_installed ___________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_missing_e0')

    def test_agy_usage_probe_missing_executable_is_not_installed(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_agy(tmp_path)
        result, _, _ = _run_agy_probe(fake, tmp_path, executable="/nonexistent/agy-xyz")
>       assert result["outcome"] == "unsupported"
E       AssertionError: assert 'error' == 'unsupported'
E         
E         - unsupported
E         + error

tests/llm_provider/test_agy_usage_probe.py:421: AssertionError
_____________ test_agy_usage_probe_rate_limit_text_is_rate_limited _____________
[gw18] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw18/test_agy_usage_probe_rate_limi0')

    def test_agy_usage_probe_rate_limit_text_is_rate_limited(
        tmp_path: Path,
    ) -> None:
        fake = _make_fake_agy(tmp_path)
        result, _, _ = _run_agy_probe(fake, tmp_path, mode="rate_limited")
        assert result["outcome"] == "error"
>       assert result["reason_code"] == "rate_limited"
E       AssertionError: assert 'timeout' == 'rate_limited'
E         
E         - rate_limited
E         + timeout

tests/llm_provider/test_agy_usage_probe.py:431: AssertionError
__ test_timed_out_summary_script_escalates_to_sigkill_when_sigterm_is_ignored __
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw0/test_timed_out_summary_script_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9c15ea9010>

    @pytest.mark.skipif(os.name != "posix", reason="process-group SIGTERM/SIGKILL")
    def test_timed_out_summary_script_escalates_to_sigkill_when_sigterm_is_ignored(
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        workspace_dir = tmp_path / "workspace"
        workspace_dir.mkdir()
        write_script(
            workspace_dir / "make_summary",
            "import signal\n"
            "import time\n"
            "signal.signal(signal.SIGTERM, signal.SIG_IGN)\n"
            "time.sleep(30)\n",
        )
        monkeypatch.setattr(
            "sase.axe.clan_summary_script.CLAN_SUMMARY_TIMEOUT_SECONDS",
            0.4,
        )
        monkeypatch.setattr(
            "sase.axe.clan_summary_script.CLAN_SUMMARY_KILL_GRACE_SECONDS",
            0.3,
        )
        signals = _spy_killpg(monkeypatch)
        started = time.monotonic()
    
        meta = extract_clan_meta(
            tmp_path,
            "summary_script=./make_summary",
            monkeypatch,
        )
    
        elapsed = time.monotonic() - started
        assert "clan_summary" not in meta
        assert signal.SIGTERM in signals
>       assert signal.SIGKILL in signals
E       assert <Signals.SIGKILL: 9> in [<Signals.SIGTERM: 15>]
E        +  where <Signals.SIGKILL: 9> = signal.SIGKILL

tests/test_clan_summary_script_execution.py:293: AssertionError
------------------------------ Captured log call -------------------------------
WARNING  sase.axe.clan_summary_script:clan_summary_script.py:137 Clan summary script './make_summary' timed out after 0.4s; omitting summary
_____________ test_failed_claim_transfer_holds_without_second_proc _____________
[gw19] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

proc = Proc(proc_id='nxb41h0jw3t9', label='true', kind='command', status='pending', command=['/bin/sh', '-c', 'true'], cwd='/...ttled_by=None, settled_at=None, finished_by=None, settlement_outcome=None, result=None, prompt_proc=None, service=None)

    def _launch_reserved(
        proc: Proc,
        *,
        fingerprint: str,
        after_spawn: Callable[[DetachedSupervisor], None] | None = None,
        after_ack: Callable[[Proc], None] | None = None,
    ) -> Proc:
        try:
            supervisor = spawn_detached_supervisor(proc.proc_id)
        except SupervisorSpawnError as exc:
            message = f"could not start proc supervisor: {_one_line(exc)}"
            settle_named_proc(
                proc.proc_id,
                supervisor_id=_starter_supervisor_id(),
                status="error",
                message=message,
                termination_reason="launch-failure",
            )
            raise ProcSubmitError(message) from exc
    
        if after_spawn is not None:
            try:
                after_spawn(supervisor)
            except Exception as exc:
                _raise_start_hook_error(proc, supervisor, exc)
    
        ack_error = wait_for_start_acknowledgement(proc.proc_id, supervisor)
        if ack_error is not None:
            terminate_supervisor(supervisor)
            _wait_for_terminal(proc.proc_id, timeout=_LAUNCH_SETTLE_SECONDS)
            current = get_proc(proc.proc_id) or proc
            if current.status not in TERMINAL_PROC_STATUSES:
                settle_named_proc(
                    proc.proc_id,
                    supervisor_id=current.supervisor_id or _starter_supervisor_id(),
                    status="error",
                    message=ack_error,
                    termination_reason="launch-failure",
                )
            raise ProcSubmitError(ack_error)
    
        current = get_proc(proc.proc_id) or proc
        if after_ack is not None:
            try:
>               after_ack(current)

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/procs/submission.py:320: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

proc = Proc(proc_id='nxb41h0jw3t9', label='true', kind='command', status='running', command=['/bin/sh', '-c', 'true'], cwd='/...ttled_by=None, settled_at=None, finished_by=None, settlement_outcome=None, result=None, prompt_proc=None, service=None)

    def after_ack(proc: Any) -> None:
        resolved_supervisor_pid = supervisor_pid(proc)
        if resolved_supervisor_pid is None:
            raise ProcSubmitError("supervisor did not report a pid")
        update_meta_field(artifacts_dir, "pid", resolved_supervisor_pid)
        if proc.supervisor_id:
            update_meta_field(
                artifacts_dir, "monitor_supervisor_identity", proc.supervisor_id
            )
        claim = claim_monitor_workspace(
            lane_start.project_file,
            lane_start.workspace_num,
            supervisor_pid=resolved_supervisor_pid,
            transfer_from_pid=lane_start.transfer_from_pid,
            artifacts_timestamp=member_timestamp,
            cl_name=lane_start.cl_name,
        )
        claim_holder["claim"] = claim
        claim_holder["pid"] = resolved_supervisor_pid
        if not claim.result.success:
            claim_error = monitor_claim_error(
                lane_start.project_file,
                lane_start.workspace_num,
                claim.result.error,
            )
>           raise ProcSubmitError(
                f"could not claim workspace for monitor: {claim_error}"
            )
E           sase.procs.submission.ProcSubmitError: could not claim workspace for monitor: workspace gone; conflicting RUNNING claim: #3 pid 4102345 workflow ace-run cl acme

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/monitor/start_launch.py:490: ProcSubmitError

During handling of the above exception, another exception occurred:

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw19/test_failed_claim_transfer_hol0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f5250ae14e0>

    def test_failed_claim_transfer_holds_without_second_proc(
        tmp_path: Path, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        dirs = stage_env(tmp_path, monkeypatch)
        staged = stage_monitor(stage_request(tmp_path, command="true"))
        dirs.append(staged.record.artifacts_dir)
    
        def _fail_claim(*args: Any, **kwargs: Any) -> Any:
            del args, kwargs
            return SimpleNamespace(
                result=SimpleNamespace(success=False, error="workspace gone"),
                starter_claim=None,
            )
    
        monkeypatch.setattr(
            "sase.monitor.start_launch.claim_monitor_workspace", _fail_claim
        )
        with pytest.raises(MonitorError, match="could not claim workspace"):
>           launch_from_persisted_payload(staged.record.artifacts_dir)

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/monitor/test_monitor_start_stage_recovery.py:222: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/monitor/start_stage_adopt.py:25: in launch_from_persisted_payload
    return launch_staged_payload(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/monitor/_start_stage_adopt_flow.py:79: in launch_staged_payload
    return _launch_from_persisted_payload_locked(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/monitor/_start_stage_adopt_flow.py:108: in _launch_from_persisted_payload_locked
    return launch_callback(context, timer)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/monitor/start_launch.py:503: in launch_monitor
    proc = submit_proc_request(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/procs/submission.py:164: in submit_proc_request
    return _launch_reserved(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/procs/submission.py:322: in _launch_reserved
    _raise_start_hook_error(current, supervisor, exc)
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/procs/submission.py:356: in _raise_start_hook_error
    settle_named_proc(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/procs/settlement.py:68: in settle_named_proc
    return _settle_named_proc_locked(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/procs/settlement.py:113: in _settle_named_proc_locked
    begun = begin_proc_settlement(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/procs/store.py:234: in begin_proc_settlement
    payload: Mapping[str, Any] = _call_binding(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'begin_proc_settlement'
args = ('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw19/test_failed_claim_transfer_hol0/.sase/procs/procs.jsonl',...ting RUNNING claim: #3 pid 4102345 workflow ace-run cl acme', 'status': 'error', ...}, 'proc_id': 'nxb41h0jw3t9', ...})
binding = <built-in function begin_proc_settlement>

    def _call_binding(name: str, *args: Any) -> Any:
        ensure_procs_migrated()
        binding = require_rust_binding(name)
        try:
>           return binding(*args)
                   ^^^^^^^^^^^^^^
E           ValueError: invalid proc "nxb41h0jw3t9": inconsistent settlement observation: frozen killed/stop/None cannot be replaced by error/launch-failure/None

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/procs/store.py:384: ValueError
_____ test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read ______
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

self = <Popen: returncode: -9 args: ('/home/bryan/.local/state/sase/workspaces/sase...>
timeout = 60

    def wait(self, timeout=None):
        """Wait for child process to terminate; returns self.returncode."""
        if timeout is not None:
            endtime = _time() + timeout
        try:
>           return self._wait(timeout=timeout)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1279: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Popen: returncode: -9 args: ('/home/bryan/.local/state/sase/workspaces/sase...>
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
E                   subprocess.TimeoutExpired: Command '('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python', '-mpytest', '--basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw2/test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read0/runpytest-0', '-p', 'no:randomly', '-c', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/pyproject.toml', '--rootdir', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_run_pytest_tmpdir.py::test_prepare_pytest_tmpdir_honors_override', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_run_pytest_health.py::test_scoped_run_lands_in_the_durable_health_store', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/widgets/test_artifact_ref_completion_catalog.py::test_commit_completion_rows_match_shared_inventory_and_resolve')' timed out after 60 seconds

/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:2076: TimeoutExpired

During handling of the above exception, another exception occurred:

pytester = <Pytester PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw2/test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read0')>

    def test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read(
        pytester: pytest.Pytester,
    ) -> None:
>       result = pytester.runpytest_subprocess(
            "-p",
            "no:randomly",
            "-c",
            str(_ROOT / "pyproject.toml"),
            "--rootdir",
            str(_ROOT),
            _LEAKING_NODE_ID,
            _MAIN_DRIVEN_LEAKING_NODE_ID,
            _DOWNSTREAM_NODE_ID,
            timeout=60,
        )
E       _pytest.pytester.Pytester.TimeoutExpired: 60 second timeout expired running: ('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python', '-mpytest', '--basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw2/test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read0/runpytest-0', '-p', 'no:randomly', '-c', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/pyproject.toml', '--rootdir', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_run_pytest_tmpdir.py::test_prepare_pytest_tmpdir_honors_override', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_run_pytest_health.py::test_scoped_run_lands_in_the_durable_health_store', '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/widgets/test_artifact_ref_completion_catalog.py::test_commit_completion_rows_match_shared_inventory_and_resolve')

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_scratch_tmpdir_leak_regression.py:59: TimeoutExpired
----------------------------- Captured stdout call -----------------------------
running: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python -mpytest --basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw2/test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read0/runpytest-0 -p no:randomly -c /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/pyproject.toml --rootdir /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_run_pytest_tmpdir.py::test_prepare_pytest_tmpdir_honors_override /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_run_pytest_health.py::test_scoped_run_lands_in_the_durable_health_store /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/widgets/test_artifact_ref_completion_catalog.py::test_commit_completion_rows_match_shared_inventory_and_resolve
     in: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw2/test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read0
______ test_title_footer_and_chooser_show_effective_and_configured_limits ______
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f9c441292b0>

    async def test_title_footer_and_chooser_show_effective_and_configured_limits(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        patch_alias_views(monkeypatch, [make_alias_view("default", "default")])
        _patch_snapshot(monkeypatch, _snapshot(override=_override()))
    
        async with ModelsPanelTestApp().run_test() as pilot:
            panel = ModelsPanel()
            pilot.app.push_screen(panel)
            await pilot.pause()
>           await wait_for(
                pilot,
                lambda: "override · 42m left" in _runner_limit_row_text(panel),
            )

tests/test_models_panel_runner_limit.py:130: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/wait.py:88: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function test_title_footer_and_chooser_show_effective_and_configured_limits.<locals>.<lambda> at 0x7f9c3187fe20>

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
E               AssertionError: wait_for(test_title_footer_and_chooser_show_effective_and_configured_limits.<locals>.<lambda>) timed out after 5.0s waiting for it to return True

src/sase/ace/testing/wait.py:54: AssertionError
_________________ test_total_timeout_settles_signaled_timeout __________________
[gw10] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw10/test_total_timeout_settles_sig0')

    def test_total_timeout_settles_signaled_timeout(tmp_path: Path) -> None:
        """Row 5: a real supervisor's total timeout is a timeout, not a bare signal."""
    
        run_id, proc_id = _submit_worker(tmp_path, ("--", "sleep", "30"), timeout_seconds=1)
        proc = wait_for_proc(proc_id, timeout=60)
        assert _result_reason(proc) == "total-timeout"
>       run = _settled_run(run_id)
              ^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/tool/test_settlement_retention.py:213: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

run_id = 'a8612aa3d52346348fbeb33df5e7b9c0'

    def _settled_run(run_id: str, *, timeout: float = 60.0) -> dict[str, Any]:
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            run = get_run(run_id)
            if run["state"] not in ("created", "running"):
                return run
            time.sleep(0.2)  # sase-test-wait: poll worker or hook settlement
>       pytest.fail(f"run {run_id} did not settle")
E       Failed: run a8612aa3d52346348fbeb33df5e7b9c0 did not settle

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/tool/test_settlement_retention.py:204: Failed
__________________ test_idle_timeout_settles_signaled_timeout __________________
[gw10] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw10/test_idle_timeout_settles_sign0')

    def test_idle_timeout_settles_signaled_timeout(tmp_path: Path) -> None:
        run_id, proc_id = _submit_worker(
            tmp_path,
            ("--", "sh", "-c", "echo started; sleep 30"),
            idle_timeout_seconds=1,
        )
        proc = wait_for_proc(proc_id, timeout=60)
        assert _result_reason(proc) == "idle-timeout"
>       run = _settled_run(run_id)
              ^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/tool/test_settlement_retention.py:232: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

run_id = '570e8740c0d5d179ce28ca1e669082c2'

    def _settled_run(run_id: str, *, timeout: float = 60.0) -> dict[str, Any]:
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            run = get_run(run_id)
            if run["state"] not in ("created", "running"):
                return run
            time.sleep(0.2)  # sase-test-wait: poll worker or hook settlement
>       pytest.fail(f"run {run_id} did not settle")
E       Failed: run 570e8740c0d5d179ce28ca1e669082c2 did not settle

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/tool/test_settlement_retention.py:204: Failed
___________ test_pytester_xdist_project_merges_worker_local_records ____________
[gw9] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

self = <Popen: returncode: -9 args: ('/home/bryan/.local/state/sase/workspaces/sase...>
timeout = 60

    def wait(self, timeout=None):
        """Wait for child process to terminate; returns self.returncode."""
        if timeout is not None:
            endtime = _time() + timeout
        try:
>           return self._wait(timeout=timeout)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:1279: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Popen: returncode: -9 args: ('/home/bryan/.local/state/sase/workspaces/sase...>
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
E                   subprocess.TimeoutExpired: Command '('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python', '-mpytest', '--basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_pytester_xdist_project_merges_worker_local_records0/runpytest-0', '-p', 'no:randomly', '-p', 'tests._visual_capture_plugin', '--sase-visual-capture-dir', '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_pytester_xdist_project_merges_worker_local_records0/capture', '--sase-visual-capture-run-id', 'run-xdist', '--sase-visual-capture-scope', 'full', '--sase-visual-capture-ace-root', 'ace_png', '--sase-visual-capture-pager-root', 'pager_png', '-n', '2', '--dist=loadfile')' timed out after 60 seconds

/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/subprocess.py:2076: TimeoutExpired

During handling of the above exception, another exception occurred:

pytester = <Pytester PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_pytester_xdist_project_merges_worker_local_records0')>
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f6cc16b1e80>

    def test_pytester_xdist_project_merges_worker_local_records(
        pytester: pytest.Pytester, monkeypatch: pytest.MonkeyPatch
    ) -> None:
        pytest.importorskip("xdist")
        _capture_pytest_env(monkeypatch)
        red = make_png(1, 1, (255, 0, 0, 255))
        blue = make_png(1, 1, (0, 0, 255, 255))
        _write_capture_project(pytester, red_hex=red.hex(), blue_hex=blue.hex())
        capture_dir = pytester.path / "capture"
        ace_root = pytester.path / "ace_png"
        pager_root = pytester.path / "pager_png"
        before = (hash_file_tree(ace_root), hash_file_tree(pager_root))
    
>       result = pytester.runpytest_subprocess(
            *_capture_args(
                capture_dir,
                extra=("-n", "2", "--dist=loadfile"),
            ),
            timeout=60,
        )
E       _pytest.pytester.Pytester.TimeoutExpired: 60 second timeout expired running: ('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python', '-mpytest', '--basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_pytester_xdist_project_merges_worker_local_records0/runpytest-0', '-p', 'no:randomly', '-p', 'tests._visual_capture_plugin', '--sase-visual-capture-dir', '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_pytester_xdist_project_merges_worker_local_records0/capture', '--sase-visual-capture-run-id', 'run-xdist', '--sase-visual-capture-scope', 'full', '--sase-visual-capture-ace-root', 'ace_png', '--sase-visual-capture-pager-root', 'pager_png', '-n', '2', '--dist=loadfile')

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_visual_capture_e2e.py:127: TimeoutExpired
----------------------------- Captured stdout call -----------------------------
running: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python -mpytest --basetemp=/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_pytester_xdist_project_merges_worker_local_records0/runpytest-0 -p no:randomly -p tests._visual_capture_plugin --sase-visual-capture-dir /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_pytester_xdist_project_merges_worker_local_records0/capture --sase-visual-capture-run-id run-xdist --sase-visual-capture-scope full --sase-visual-capture-ace-root ace_png --sase-visual-capture-pager-root pager_png -n 2 --dist=loadfile
     in: /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw9/test_pytester_xdist_project_merges_worker_local_records0
_________________ test_handoff_end_to_end_settles_through_proc _________________
[gw20] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f0b0b4eef90>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw20/test_handoff_end_to_end_settle0')
capsys = <_pytest.capture.CaptureFixture object at 0x7f0b0b5b6cd0>

    def test_handoff_end_to_end_settles_through_proc(
        monkeypatch: pytest.MonkeyPatch, tmp_path: Path, capsys: pytest.CaptureFixture[str]
    ) -> None:
        _clean_env(monkeypatch, tmp_path)
        from sase.procs import read_procs, wait_for_proc
    
        started = time.monotonic()
        code = execute_tool_run(_handoff_request("--", "sh", "-c", "sleep 2; exit 7"))
        elapsed = time.monotonic() - started
        assert code == 0
>       assert elapsed < 2.0
E       assert 2.166832898001303 < 2.0

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/tool/test_handoff.py:175: AssertionError
----------------------------- Captured stdout call -----------------------------
sase tool run 8ba9d2a94dcb8d12618d7ad0321fb27a
tool: ad-hoc
proc: 1wnb3q7y6h91
the run may still be starting
monitor with: sase tool show 8ba9d2a94dcb8d12618d7ad0321fb27a -F
wait with: sase tool wait 8ba9d2a94dcb8d12618d7ad0321fb27a
stop with: sase tool stop 8ba9d2a94dcb8d12618d7ad0321fb27a
proc log with: sase proc show 1wnb3q7y6h91 --follow
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

tests/ace/tui/test_agent_archive_view_foundation.py::test_open_moves_detail_ownership_to_archive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:967: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    def __init__(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_foreground_submit_runs_in_terminal_and_records
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/json/decoder.py:361: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._record_local_history.<locals>._record' was never awaited
    obj, end = self.scan_once(s, idx)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_submit.py::test_tail_polling_never_touches_message_pump
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/command_line/test_panel_shell_submit.py:175: DeprecationWarning: 'asyncio.iscoroutinefunction' is deprecated and slated for removal in Python 3.16; use inspect.iscoroutinefunction() instead
    assert asyncio.iscoroutinefunction(CommandLineTranscript._tail_loop)

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object _recheck_grammar_key at 0x7f6cf7b72020>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/modals/test_new_project_create_execution.py::test_create_review_renders_danger_heading_and_keep_notice
  <string>:9: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_memory_pane_changes_lens_review.py::test_changes_lens_shows_review_chip_and_dots
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/textual/css/stylesheet.py:543: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    initial_defaults: set[str] = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object _record_history_async.<locals>._record at 0x7f6cda54d6d0>: None
  
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while finalizing coroutine <coroutine object CommandLineScreen._load_tail_worker at 0x7f8ed7b374c0>: None
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/test_agent_archive_column_actions_interaction.py::test_cursor_survives_a_rebuild_and_falls_to_a_neighbor_when_row_vanishes
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/_agent_archive_column_helpers.py:49: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    "last_activity_at": f"{day}T{hour:02d}:00:00Z",
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/ace/tui/_agent_archive_controller_helpers.py:149: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    async def _immediate(fn: Any) -> Any:
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_panel_hint_folding.py::test_hint_enumeration_includes_clan_and_agent_session_fold_owners
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

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=4100503) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=4100430) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

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

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

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

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

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

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=4100623) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=4100902) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

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

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=4102345) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

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

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

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

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/macro/workflow_runner.py:477: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_staged_reconcile_crashes.py::test_gate_publication_survives_process_death_before_outer_receipt
tests/test_staged_reconcile_crashes.py::test_monitor_submit_survives_process_death_and_scheduler_reuses_proc
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:76: DeprecationWarning: This process (pid=4102129) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
782.49s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
774.88s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
542.07s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
479.47s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
401.89s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
397.83s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
354.29s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
316.71s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
304.01s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
293.44s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
267.83s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
244.96s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
234.56s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
219.49s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
201.42s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
188.37s setup    tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
184.90s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
172.85s call     tests/test_markdown_print_width.py::test_only_the_width_authority_binds_a_width_to_an_integer_literal
171.86s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
168.48s call     tests/test_markdown_print_width.py::test_no_module_snapshots_the_width_at_import_time
=========================== short test summary info ============================
FAILED tests/ace/tui/modals/test_preview_panel_image_modal.py::test_image_modal_resize_rerenders_with_new_viewport
FAILED tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
FAILED tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_stuck_loading_card_clears_on_pulse
FAILED tests/ace/tui/test_agent_archive_column_app.py::test_clicking_a_banner_toggles_it_like_enter
FAILED tests/ace/tui/test_agent_cleanup_panel_clan_sticky_e2e.py::test_cleanup_dismiss_partial_clan_keeps_panel_and_container
FAILED tests/ace/tui/test_node_jump_ladder.py::test_real_ace_page_query_clear_retry_records_the_live_transition
FAILED tests/llm_provider/test_usage_refresh_runner.py::test_runner_collects_synthetic_provider
FAILED tests/ace/tui/test_screenshot_export.py::test_app_export_body_tolerates_signal_task_refresh_wait_error
FAILED tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_mints_with_the_minimal_echo_sequence
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_scopes_the_session_to_the_probe_directory
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_preserves_over_quota_percentages
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_malformed_usage_is_a_structured_error
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_aborts_before_any_turn_when_the_session_is_not_echo[guard_provider]
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_aborts_before_any_turn_when_the_session_is_not_echo[guard_model]
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_session_without_a_session_object_is_malformed
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_unexpected_turn_ack_is_vendor_drift
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_rejected_turn_is_vendor_drift
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_missing_usage_method_is_vendor_drift
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_other_host_errors_are_probe_failures
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_rate_limit_error_is_rate_limited
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_transport_failure_with_rate_limit_stderr_is_rate_limited
FAILED tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_refuses_unsolicited_host_requests
FAILED tests/fakey/test_monitor_capacity_zero_weight_wait_e2e.py::test_zero_weight_wait_monitor_followup_reenters_full_host_admission
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_collects_native_weekly_billing
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_decodes_verified_legacy_monthly_ratio
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_missing_billing_method_is_vendor_drift
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_auth_required_is_unauthenticated
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_rate_limit_is_rate_limited
FAILED tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_transport_failure_with_rate_limit_stderr_is_rate_limited
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_explicit_ineligible_accounts_are_not_applicable[Free]
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_explicit_ineligible_accounts_are_not_applicable[Enterprise]
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_api_auth_evidence_is_not_applicable
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_absent_config_without_evidence_is_malformed
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_identity_mismatch_is_unsupported
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_missing_period_is_partial
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_missing_percentage_is_malformed
FAILED tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_reparents_the_supervisor_before_return
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_omitted_zero_unified_weekly_is_complete[None]
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_omitted_zero_unified_weekly_is_complete[string]
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_omitted_zero_unified_weekly_is_complete[nested]
FAILED tests/monitor/test_monitor_start_supervisor.py::test_ppid_walk_teardown_of_starter_descendants_leaves_monitor_running
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_omitted_zero_unified_monthly_and_explicit_zero
FAILED tests/monitor/test_monitor_start_supervisor.py::test_sighup_to_supervisor_does_not_stop_the_monitor
FAILED tests/llm_provider/test_usage_probe.py::test_descendant_processes_are_reaped
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_empty_used_object_is_zero
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_invalid_explicit_percent_is_malformed[None]
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_invalid_explicit_percent_is_malformed[True]
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_invalid_explicit_percent_is_malformed[0]
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_invalid_explicit_percent_is_malformed[-1.0]
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_false_unified_marker_stays_malformed
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_native_plan_label_beats_camel_case
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_over_100_percent_is_preserved
FAILED tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_reaps_descendant_processes
FAILED tests/pager/test_rendered_link_contract.py::test_file_backed_home_path_hint_uses_filesystem_resolution
FAILED tests/sdd_store/test_sdd_git_streaming.py::test_streaming_transfer_succeeds_while_progress_continues
FAILED tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
FAILED tests/pager/test_bead_live_links.py::test_pager_follows_bead_links_and_preserves_trail
FAILED tests/pager/test_view_leak.py::test_split_open_and_close_releases_both_panes
FAILED tests/ace/tui/test_statistics_footprint.py::test_footprint_finder_filters_and_drills_to_area
FAILED tests/test_sudo_ledger_settlement.py::test_sudo_answer_waits_for_concurrent_reclaimer_without_failure
FAILED tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued
FAILED tests/agents_sync/test_commit_publication_bounded_drain.py::test_manifest_timeout_cleans_regenerable_paths_and_preserves_objects
FAILED tests/agents_sync/test_commit_publication_bounded_drain.py::test_after_a_blocked_render_a_later_drain_retries_and_succeeds
FAILED tests/agents_sync/test_publication_cleanup_policy.py::test_policy_lookup_failure_preserves_drain_timeout_attribution
FAILED tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_with_young_index_lock_is_bounded
FAILED tests/llm_provider/test_codex_usage_probe.py::test_descendant_processes_are_reaped
FAILED tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_kills_the_whole_process_group_on_timeout
FAILED tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_times_out_continuous_output
FAILED tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_times_out_after_partial_line
FAILED tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_chatty_command_does_not_hit_idle_timeout
FAILED tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_escalates_term_ignoring_chatty_child
FAILED tests/llm_provider/test_muse_provider_stream.py::test_muse_stream_framing_under_provider_timer_in_a_pty
FAILED tests/footprint/test_catalog.py::test_every_command_spec_has_an_id - A...
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_collects_four_windows
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_old_version_never_spawns_usage
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_unparseable_version_never_spawns_usage
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_failed_version_probe_is_unsupported
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_auth_prompt_is_logged_out_fast
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_hang_is_timeout_and_reaps_child
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_malformed_stdout_is_parse_error
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_omitted_zero_row_is_exhausted
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_turn_ran_is_vendor_drift
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_missing_executable_is_not_installed
FAILED tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_rate_limit_text_is_rate_limited
FAILED tests/test_clan_summary_script_execution.py::test_timed_out_summary_script_escalates_to_sigkill_when_sigterm_is_ignored
FAILED tests/monitor/test_monitor_start_stage_recovery.py::test_failed_claim_transfer_holds_without_second_proc
FAILED tests/test_scratch_tmpdir_leak_regression.py::test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read
FAILED tests/test_models_panel_runner_limit.py::test_title_footer_and_chooser_show_effective_and_configured_limits
FAILED tests/tool/test_settlement_retention.py::test_total_timeout_settles_signaled_timeout
FAILED tests/tool/test_settlement_retention.py::test_idle_timeout_settles_signaled_timeout
FAILED tests/test_visual_capture_e2e.py::test_pytester_xdist_project_merges_worker_local_records
FAILED tests/tool/test_handoff.py::test_handoff_end_to_end_settles_through_proc
=== 94 failed, 60475 passed, 20 skipped, 112 warnings in 4709.74s (1:18:29) ====
[contention-diag] +4710s soak 2p/2t rss 0.4G pss 0.4G swap 0.1G majflt 15660 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G | host avail 40.0G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 2.06/0.0 io 3.64 cpu 11.02 | cgroup 1.7G/16106127360 oom_kill 0 | free scratch 327.9G/45380289i tmp 30.3G/1035583i workspace 327.9G/45380289i | scratch used 0.7G in 128271 entries (truncated) | repeat-01 collected 26/26 workers (60588 items) tests 60588 done 94 failed | 11 hazardous kill call(s)
[contention-diag] +4716s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 395 | 1 parent rss 0.0G pss 0.0G | host avail 40.3G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 1.13/0.0 io 5.24 cpu 6.05 | cgroup 1.3G/16106127360 oom_kill 0 | free scratch 327.9G/45380289i tmp 30.3G/1035583i workspace 327.9G/45380289i | repeat-01 collected 26/26 workers (60588 items) tests 60588 done 94 failed | 11 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4716s, 306 samples, 0 signal(s); peaks: cgroup_current 15.0G, min_free_scratch 327.9G, min_free_tmp 30.3G, min_free_workspace 327.9G, min_inodes_scratch 45320051, min_inodes_tmp 1035548, min_inodes_workspace 45320051, min_mem_available 11.0G, min_swap_free 48.5G, oom_kill_delta 0, pressure_memory_full 8.11, pswpin_delta 1304571, pswpout_delta 1835374, scratch_bytes 0.7G, soak_procs 48, soak_pss 14.5G, soak_rss 15.9G, soak_swap 2.7G, soak_threads 250

contention tally: 94 node(s) failed across 1 repeat(s) in 4716.1s; red repeats: 1
  1/1  tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke  (repeats 1)
  1/1  tests/ace/tui/modals/test_preview_panel_image_modal.py::test_image_modal_resize_rerenders_with_new_viewport  (repeats 1)
  1/1  tests/ace/tui/test_agent_archive_column_app.py::test_clicking_a_banner_toggles_it_like_enter  (repeats 1)
  1/1  tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_stuck_loading_card_clears_on_pulse  (repeats 1)
  1/1  tests/ace/tui/test_agent_cleanup_panel_clan_sticky_e2e.py::test_cleanup_dismiss_partial_clan_keeps_panel_and_container  (repeats 1)
  1/1  tests/ace/tui/test_node_jump_ladder.py::test_real_ace_page_query_clear_retry_records_the_live_transition  (repeats 1)
  1/1  tests/ace/tui/test_screenshot_export.py::test_app_export_body_tolerates_signal_task_refresh_wait_error  (repeats 1)
  1/1  tests/ace/tui/test_statistics_footprint.py::test_footprint_finder_filters_and_drills_to_area  (repeats 1)
  1/1  tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive  (repeats 1)
  1/1  tests/ace/tui/test_update_toast_startup.py::test_startup_update_toast_appears_once_in_tui  (repeats 1)
  1/1  tests/agents_sync/test_commit_publication_bounded_drain.py::test_after_a_blocked_render_a_later_drain_retries_and_succeeds  (repeats 1)
  1/1  tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_is_bounded_and_leaves_the_request_queued  (repeats 1)
  1/1  tests/agents_sync/test_commit_publication_bounded_drain.py::test_blocked_render_with_young_index_lock_is_bounded  (repeats 1)
  1/1  tests/agents_sync/test_commit_publication_bounded_drain.py::test_manifest_timeout_cleans_regenerable_paths_and_preserves_objects  (repeats 1)
  1/1  tests/agents_sync/test_publication_cleanup_policy.py::test_policy_lookup_failure_preserves_drain_timeout_attribution  (repeats 1)
  1/1  tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap  (repeats 1)
  1/1  tests/fakey/test_monitor_capacity_zero_weight_wait_e2e.py::test_zero_weight_wait_monitor_followup_reenters_full_host_admission  (repeats 1)
  1/1  tests/footprint/test_catalog.py::test_every_command_spec_has_an_id  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_auth_prompt_is_logged_out_fast  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_collects_four_windows  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_failed_version_probe_is_unsupported  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_hang_is_timeout_and_reaps_child  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_malformed_stdout_is_parse_error  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_missing_executable_is_not_installed  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_old_version_never_spawns_usage  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_omitted_zero_row_is_exhausted  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_rate_limit_text_is_rate_limited  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_turn_ran_is_vendor_drift  (repeats 1)
  1/1  tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_unparseable_version_never_spawns_usage  (repeats 1)
  1/1  tests/llm_provider/test_codex_usage_probe.py::test_descendant_processes_are_reaped  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_transport_failure_with_rate_limit_stderr_is_rate_limited  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_absent_config_without_evidence_is_malformed  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_api_auth_evidence_is_not_applicable  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_auth_required_is_unauthenticated  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_collects_native_weekly_billing  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_decodes_verified_legacy_monthly_ratio  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_empty_used_object_is_zero  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_explicit_ineligible_accounts_are_not_applicable[Enterprise]  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_explicit_ineligible_accounts_are_not_applicable[Free]  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_false_unified_marker_stays_malformed  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_identity_mismatch_is_unsupported  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_invalid_explicit_percent_is_malformed[-1.0]  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_invalid_explicit_percent_is_malformed[0]  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_invalid_explicit_percent_is_malformed[None]  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_invalid_explicit_percent_is_malformed[True]  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_missing_billing_method_is_vendor_drift  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_missing_percentage_is_malformed  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_missing_period_is_partial  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_native_plan_label_beats_camel_case  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_omitted_zero_unified_monthly_and_explicit_zero  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_omitted_zero_unified_weekly_is_complete[None]  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_omitted_zero_unified_weekly_is_complete[nested]  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_omitted_zero_unified_weekly_is_complete[string]  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_over_100_percent_is_preserved  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_rate_limit_is_rate_limited  (repeats 1)
  1/1  tests/llm_provider/test_grok_usage_probe.py::test_grok_usage_probe_reaps_descendant_processes  (repeats 1)
  1/1  tests/llm_provider/test_muse_provider_stream.py::test_muse_stream_framing_under_provider_timer_in_a_pty  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_transport_failure_with_rate_limit_stderr_is_rate_limited  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_aborts_before_any_turn_when_the_session_is_not_echo[guard_model]  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_aborts_before_any_turn_when_the_session_is_not_echo[guard_provider]  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_malformed_usage_is_a_structured_error  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_mints_with_the_minimal_echo_sequence  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_missing_usage_method_is_vendor_drift  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_other_host_errors_are_probe_failures  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_preserves_over_quota_percentages  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_rate_limit_error_is_rate_limited  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_refuses_unsolicited_host_requests  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_rejected_turn_is_vendor_drift  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_scopes_the_session_to_the_probe_directory  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_session_without_a_session_object_is_malformed  (repeats 1)
  1/1  tests/llm_provider/test_muse_usage_probe.py::test_muse_usage_probe_unexpected_turn_ack_is_vendor_drift  (repeats 1)
  1/1  tests/llm_provider/test_usage_probe.py::test_descendant_processes_are_reaped  (repeats 1)
  1/1  tests/llm_provider/test_usage_refresh_runner.py::test_runner_collects_synthetic_provider  (repeats 1)
  1/1  tests/monitor/test_monitor_start_stage_recovery.py::test_failed_claim_transfer_holds_without_second_proc  (repeats 1)
  1/1  tests/monitor/test_monitor_start_supervisor.py::test_ppid_walk_teardown_of_starter_descendants_leaves_monitor_running  (repeats 1)
  1/1  tests/monitor/test_monitor_start_supervisor.py::test_sighup_to_supervisor_does_not_stop_the_monitor  (repeats 1)
  1/1  tests/monitor/test_monitor_start_supervisor.py::test_start_monitor_reparents_the_supervisor_before_return  (repeats 1)
  1/1  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_chatty_command_does_not_hit_idle_timeout  (repeats 1)
  1/1  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_escalates_term_ignoring_chatty_child  (repeats 1)
  1/1  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_kills_the_whole_process_group_on_timeout  (repeats 1)
  1/1  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_times_out_after_partial_line  (repeats 1)
  1/1  tests/monitor/test_monitor_supervise_timeout.py::test_run_supervisor_times_out_continuous_output  (repeats 1)
  1/1  tests/pager/test_bead_live_links.py::test_pager_follows_bead_links_and_preserves_trail  (repeats 1)
  1/1  tests/pager/test_rendered_link_contract.py::test_file_backed_home_path_hint_uses_filesystem_resolution  (repeats 1)
  1/1  tests/pager/test_view_leak.py::test_split_open_and_close_releases_both_panes  (repeats 1)
  1/1  tests/sdd_store/test_sdd_git_streaming.py::test_streaming_transfer_succeeds_while_progress_continues  (repeats 1)
  1/1  tests/test_clan_summary_script_execution.py::test_timed_out_summary_script_escalates_to_sigkill_when_sigterm_is_ignored  (repeats 1)
  1/1  tests/test_models_panel_runner_limit.py::test_title_footer_and_chooser_show_effective_and_configured_limits  (repeats 1)
  1/1  tests/test_scratch_tmpdir_leak_regression.py::test_prepare_pytest_tmpdir_leak_does_not_break_a_later_scratch_read  (repeats 1)
  1/1  tests/test_sudo_ledger_settlement.py::test_sudo_answer_waits_for_concurrent_reclaimer_without_failure  (repeats 1)
  1/1  tests/test_visual_capture_e2e.py::test_pytester_xdist_project_merges_worker_local_records  (repeats 1)
  1/1  tests/tool/test_handoff.py::test_handoff_end_to_end_settles_through_proc  (repeats 1)
  1/1  tests/tool/test_settlement_retention.py::test_idle_timeout_settles_signaled_timeout  (repeats 1)
  1/1  tests/tool/test_settlement_retention.py::test_total_timeout_settles_signaled_timeout  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics
error: recipe `test-contention` failed on line 779 with exit code 1

