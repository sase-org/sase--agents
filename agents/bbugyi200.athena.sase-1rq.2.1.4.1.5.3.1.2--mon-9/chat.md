# Chat History - ace-run (sase-1rq.2.1.4.1.5.3.1.2--mon-9)

- **TIMESTAMP:** 2026-11-09 14:33:57 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1rq.2.1.4.1.5.3.1.2--mon-9

## Prompt

sase monitor start --command 'set --; i=0; while [ "$i" -lt 13 ]; do set -- "$@" tests/ace/tui/test_config_transaction_widget.py tests/ace/tui/test_statistics_pane_filters.py tests/pager/test_app_dangling.py tests/completion/test_update_refresh_soak.py tests/test_output.py tests/ace/tui/test_agent_archive_column_app.py tests/ace/tui/modals/test_memory_panel.py tests/ace/tui/util/test_stall_watchdog_suspend.py tests/test_models_panel_usage_modal.py; i=$((i + 1)); done; SASE_CONTENTION_CPUS=0,1 SASE_CONTENTION_WORKERS=26 SASE_CONTENTION_REPEAT=1 just test-contention -- --keep-duplicates "$@"' --reason 'Rerun recent contention failure families after Archive focus-transfer repair'

## Response

sase tool run cbd6f7071eaf19cdb26ebbe2ade5dae5
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.44.2 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs==0.43.2` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_pin` moves the published pin on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs pin in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published pin at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-contention          │
└───────────────────────────────────────────────────────┘

---------- Running default-lane pytest contention harness... ----------
contention soak: 1 repeat(s), 26 workers, dist=worksteal

---------- contention repeat 1/1 ----------
[contention-diag] root pid 2867704, sampler pid 2867705 on cpus 0-63 (soak cpus 0-1), python 3.14.7, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-2160861-1794251947096970663.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 31.7G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.94 cpu 0.0 | cgroup 0.2G/max oom_kill 0 | free scratch 282.7G/44576512i tmp 25.4G/976285i workspace 282.7G/44576512i | scratch used 0.0G in 3013 entries | progress none yet
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +15s soak 28p/80t rss 2.4G pss 2.1G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 2.2G pss 1.9G | host avail 33.4G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.9 cpu 9.76 | cgroup 2.3G/max oom_kill 0 | free scratch 282.4G/44576440i tmp 25.4G/976285i workspace 282.4G/44576440i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +30s soak 28p/80t rss 4.3G pss 3.8G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 4.1G pss 3.6G | host avail 29.5G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.58 cpu 14.1 | cgroup 4.0G/max oom_kill 0 | free scratch 282.2G/44576431i tmp 25.4G/976285i workspace 282.2G/44576431i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +46s soak 28p/80t rss 5.6G pss 5.1G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 5.4G pss 4.8G | host avail 31.4G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.26 cpu 11.98 | cgroup 5.2G/max oom_kill 0 | free scratch 282.8G/44577445i tmp 25.4G/976285i workspace 282.8G/44577445i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +61s soak 28p/80t rss 6.2G pss 5.6G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 5.9G pss 5.4G | host avail 30.4G/62.7G swapfree 45.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.55 cpu 11.29 | cgroup 5.8G/max oom_kill 0 | free scratch 282.8G/44577728i tmp 25.4G/976285i workspace 282.8G/44577728i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +76s soak 28p/80t rss 6.6G pss 6.1G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.4G pss 5.8G | host avail 30.0G/62.7G swapfree 45.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.07 cpu 11.31 | cgroup 6.3G/max oom_kill 0 | free scratch 282.8G/44577778i tmp 25.4G/976285i workspace 282.8G/44577778i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +91s soak 28p/80t rss 6.8G pss 6.3G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.6G pss 6.1G | host avail 28.5G/62.7G swapfree 45.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.05 cpu 12.57 | cgroup 6.5G/max oom_kill 0 | free scratch 282.8G/44577768i tmp 25.4G/976285i workspace 282.8G/44577768i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +106s soak 28p/80t rss 6.9G pss 6.3G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.6G pss 6.1G | host avail 27.5G/62.7G swapfree 45.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.08 cpu 12.68 | cgroup 6.5G/max oom_kill 0 | free scratch 283.3G/44636922i tmp 25.4G/976285i workspace 283.3G/44636922i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +122s soak 28p/80t rss 7.2G pss 6.6G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.9G pss 6.4G | host avail 28.4G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.72 cpu 13.16 | cgroup 6.9G/max oom_kill 0 | free scratch 283.0G/44614742i tmp 25.3G/975955i workspace 283.0G/44614742i | scratch used 0.0G in 3042 entries | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +137s soak 28p/80t rss 7.6G pss 7.0G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.3G pss 6.8G | host avail 27.8G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.9/0.72 io 7.83 cpu 11.38 | cgroup 7.2G/max oom_kill 0 | free scratch 282.8G/44609433i tmp 25.4G/976164i workspace 282.8G/44609433i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +152s soak 28p/80t rss 7.7G pss 7.1G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.4G pss 6.9G | host avail 27.1G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.22/0.17 io 4.73 cpu 13.86 | cgroup 7.3G/max oom_kill 0 | free scratch 282.8G/44609096i tmp 25.4G/976239i workspace 282.8G/44609096i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +168s soak 28p/80t rss 7.7G pss 7.1G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.4G pss 6.9G | host avail 31.2G/62.7G swapfree 45.1G/64.0G oom_kill +0 | psi10 mem 0.51/0.5 io 2.69 cpu 20.14 | cgroup 7.3G/max oom_kill 0 | free scratch 282.8G/44608939i tmp 25.4G/976239i workspace 282.8G/44608939i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +183s soak 28p/80t rss 7.7G pss 7.2G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.5G pss 7.0G | host avail 28.7G/62.7G swapfree 45.1G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 1.75 cpu 18.66 | cgroup 7.4G/max oom_kill 0 | free scratch 282.8G/44609098i tmp 25.4G/976248i workspace 282.8G/44609098i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +198s soak 28p/80t rss 8.0G pss 7.5G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.8G pss 7.2G | host avail 27.7G/62.7G swapfree 45.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.68 cpu 12.76 | cgroup 7.7G/max oom_kill 0 | free scratch 282.8G/44609247i tmp 25.4G/976259i workspace 282.8G/44609247i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +213s soak 28p/80t rss 8.0G pss 7.5G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.8G pss 7.3G | host avail 30.0G/62.7G swapfree 45.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.99 cpu 17.75 | cgroup 7.7G/max oom_kill 0 | free scratch 282.8G/44609198i tmp 25.4G/976259i workspace 282.8G/44609198i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +229s soak 28p/80t rss 8.0G pss 7.5G swap 0.0G majflt 2 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.8G pss 7.3G | host avail 28.0G/62.7G swapfree 45.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.22 cpu 15.65 | cgroup 7.7G/max oom_kill 0 | free scratch 282.7G/44608282i tmp 25.4G/976257i workspace 282.7G/44608282i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +244s soak 28p/80t rss 8.3G pss 7.7G swap 0.0G majflt 4 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.0G pss 7.5G | host avail 27.7G/62.7G swapfree 45.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.92 cpu 13.88 | cgroup 8.0G/max oom_kill 0 | free scratch 282.6G/44607672i tmp 25.4G/976258i workspace 282.6G/44607672i | scratch used 0.0G in 3042 entries | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +259s soak 28p/80t rss 8.6G pss 8.0G swap 0.0G majflt 4 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.3G pss 7.8G | host avail 29.4G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.53 cpu 13.64 | cgroup 8.3G/max oom_kill 0 | free scratch 282.3G/44607072i tmp 25.4G/976258i workspace 282.3G/44607072i | repeat-01 collected 18/26 workers (1105 items) tests 0 done 0 failed
26 workers [1105 items]

...........................................[contention-diag] +275s soak 28p/155t rss 8.9G pss 8.2G swap 0.0G majflt 105 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.6G pss 7.9G | host avail 28.7G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.49 cpu 10.44 | cgroup 8.4G/max oom_kill 0 | free scratch 282.4G/44605888i tmp 25.4G/976257i workspace 282.4G/44605888i | repeat-01 collected 26/26 workers (1105 items) tests 42 done 0 failed | 26 in flight, oldest 15s gw0 tests/ace/tui/test_config_transaction_widget.py::test_apply_conflict_preserves_draft_and_returns_to_replan
[contention-diag] +290s soak 28p/175t rss 8.9G pss 8.2G swap 0.0G majflt 117 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.7G pss 8.0G | host avail 27.0G/62.7G swapfree 45.3G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 0.1 cpu 10.89 | cgroup 8.5G/max oom_kill 0 | free scratch 282.9G/44605555i tmp 25.4G/976257i workspace 282.9G/44605555i | repeat-01 collected 26/26 workers (1105 items) tests 42 done 0 failed | 26 in flight, oldest 30s gw0 tests/ace/tui/test_config_transaction_widget.py::test_apply_conflict_preserves_draft_and_returns_to_replan
[contention-diag] +305s soak 31p/247t rss 9.1G pss 8.3G swap 0.0G majflt 191 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.9G pss 8.1G, 3 descendant rss 0.0G pss 0.0G | host avail 26.1G/62.7G swapfree 45.3G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.01 cpu 10.89 | cgroup 8.5G/max oom_kill 0 | free scratch 282.5G/44604942i tmp 25.4G/976257i workspace 282.5G/44604942i | repeat-01 collected 26/26 workers (1105 items) tests 42 done 0 failed | 26 in flight, oldest 45s gw0 tests/ace/tui/test_config_transaction_widget.py::test_apply_conflict_preserves_draft_and_returns_to_replan
.................[contention-diag] +321s soak 28p/209t rss 9.3G pss 8.4G swap 0.0G majflt 196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.0G pss 8.2G | host avail 25.4G/62.7G swapfree 45.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 11.35 | cgroup 8.7G/max oom_kill 0 | free scratch 282.2G/44604415i tmp 25.4G/976258i workspace 282.2G/44604415i | repeat-01 collected 26/26 workers (1105 items) tests 59 done 0 failed | 26 in flight, oldest 61s gw4 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_a_banner_toggles_it_like_enter
............ [  1%]
.............[contention-diag] +336s soak 28p/179t rss 9.3G pss 8.4G swap 0.0G majflt 196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.0G pss 8.2G | host avail 25.7G/62.7G swapfree 45.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.33 cpu 14.41 | cgroup 8.7G/max oom_kill 0 | free scratch 282.0G/44604211i tmp 25.4G/976258i workspace 282.0G/44604211i | repeat-01 collected 26/26 workers (1105 items) tests 85 done 0 failed | 26 in flight, oldest 24s gw0 tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
...................[contention-diag] +351s soak 28p/214t rss 9.3G pss 8.5G swap 0.0G majflt 196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.2G | host avail 23.2G/62.7G swapfree 45.3G/64.0G oom_kill +0 | psi10 mem 0.29/0.29 io 1.78 cpu 13.61 | cgroup 8.7G/max oom_kill 0 | free scratch 282.0G/44603963i tmp 25.4G/976256i workspace 282.0G/44603963i | repeat-01 collected 26/26 workers (1105 items) tests 103 done 0 failed | 26 in flight, oldest 38s gw23 tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
.......................................[contention-diag] +367s soak 28p/215t rss 9.3G pss 8.5G swap 0.0G majflt 196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 24.6G/62.7G swapfree 45.3G/64.0G oom_kill +0 | psi10 mem 0.1/0.1 io 0.93 cpu 15.56 | cgroup 8.7G/max oom_kill 0 | free scratch 282.2G/44603665i tmp 25.4G/976258i workspace 282.2G/44603665i | scratch used 0.0G in 4667 entries | repeat-01 collected 26/26 workers (1105 items) tests 143 done 0 failed | 26 in flight, oldest 45s gw13 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
. [  4%]
.....................................[contention-diag] +382s soak 28p/207t rss 9.4G pss 8.5G swap 0.0G majflt 196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 24.3G/62.7G swapfree 45.3G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.97 cpu 16.2 | cgroup 8.8G/max oom_kill 0 | free scratch 282.2G/44603423i tmp 25.4G/976258i workspace 282.2G/44603423i | repeat-01 collected 26/26 workers (1105 items) tests 178 done 0 failed | 26 in flight, oldest 48s gw17 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
................................... [  4%]
.................................[contention-diag] +397s soak 28p/160t rss 9.4G pss 8.5G swap 0.0G majflt 197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 23.1G/62.7G swapfree 45.3G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 1.34 cpu 18.53 | cgroup 8.8G/max oom_kill 0 | free scratch 282.2G/44603190i tmp 25.4G/976258i workspace 282.2G/44603190i | repeat-01 collected 26/26 workers (1105 items) tests 248 done 0 failed | 26 in flight, oldest 43s gw12 tests/ace/tui/test_statistics_pane_filters.py::test_range_and_project_group_switches_coalesce_to_latest_selection
....................................... [  4%]
..............[contention-diag] +412s soak 28p/203t rss 9.3G pss 8.5G swap 0.0G majflt 197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.0G pss 8.3G | host avail 19.8G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.34/0.34 io 2.44 cpu 19.28 | cgroup 8.9G/max oom_kill 0 | free scratch 282.2G/44602920i tmp 25.4G/976258i workspace 282.2G/44602920i | repeat-01 collected 26/26 workers (1105 items) tests 302 done 0 failed | 26 in flight, oldest 39s gw13 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
...........................................[contention-diag] +428s soak 28p/223t rss 9.3G pss 8.5G swap 0.0G majflt 197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.0G pss 8.3G | host avail 19.0G/62.7G swapfree 44.8G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 1.33 cpu 14.04 | cgroup 8.9G/max oom_kill 0 | free scratch 281.9G/44601993i tmp 25.4G/976258i workspace 281.9G/44601993i | repeat-01 collected 26/26 workers (1105 items) tests 345 done 0 failed | 25 in flight, oldest 55s gw13 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
............... [  4%]
..................................................................[contention-diag] +443s soak 28p/202t rss 9.3G pss 8.6G swap 0.0G majflt 197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 20.4G/62.7G swapfree 44.5G/64.0G oom_kill +0 | psi10 mem 0.18/0.12 io 0.98 cpu 11.58 | cgroup 8.9G/max oom_kill 0 | free scratch 281.3G/44601836i tmp 25.4G/976258i workspace 281.3G/44601836i | repeat-01 collected 26/26 workers (1105 items) tests 422 done 0 failed | 26 in flight, oldest 53s gw10 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_the_pulse_returns_to_the_inbox
...... [  5%]
................................................[contention-diag] +459s soak 28p/181t rss 9.3G pss 8.6G swap 0.0G majflt 197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 21.0G/62.7G swapfree 44.5G/64.0G oom_kill +0 | psi10 mem 0.03/0.02 io 0.89 cpu 11.22 | cgroup 8.9G/max oom_kill 0 | free scratch 281.9G/44599694i tmp 25.4G/976258i workspace 281.9G/44599694i | repeat-01 collected 26/26 workers (1105 items) tests 474 done 0 failed | 26 in flight, oldest 62s gw5 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
........................ [  6%]
...................................[contention-diag] +474s soak 28p/207t rss 9.3G pss 8.6G swap 0.0G majflt 197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 26.8G/62.7G swapfree 44.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.83 cpu 10.4 | cgroup 8.9G/max oom_kill 0 | free scratch 281.9G/44600721i tmp 25.4G/976258i workspace 281.9G/44600721i | repeat-01 collected 26/26 workers (1105 items) tests 539 done 0 failed | 26 in flight, oldest 40s gw13 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_the_pulse_returns_to_the_inbox
..................................... [  6%]
.....[contention-diag] +489s soak 28p/214t rss 9.3G pss 8.6G swap 0.0G majflt 197 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 26.9G/62.7G swapfree 44.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.35 cpu 15.39 | cgroup 8.9G/max oom_kill 0 | free scratch 281.7G/44600635i tmp 25.4G/976255i workspace 281.7G/44600635i | scratch used 0.0G in 6366 entries | repeat-01 collected 26/26 workers (1105 items) tests 579 done 0 failed | 26 in flight, oldest 54s gw14 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_the_pulse_returns_to_the_inbox
..........................................[contention-diag] +505s soak 28p/206t rss 9.3G pss 8.6G swap 0.0G majflt 201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 25.1G/62.7G swapfree 44.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.81 cpu 13.5 | cgroup 8.9G/max oom_kill 0 | free scratch 281.5G/44599858i tmp 25.4G/976253i workspace 281.5G/44599858i | repeat-01 collected 26/26 workers (1105 items) tests 622 done 0 failed | 26 in flight, oldest 56s gw2 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
......................... [  6%]
...[contention-diag] +520s soak 28p/188t rss 9.4G pss 8.6G swap 0.0G majflt 201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 23.1G/62.7G swapfree 44.5G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 1.6 cpu 12.5 | cgroup 8.9G/max oom_kill 0 | free scratch 281.3G/44599183i tmp 25.4G/976253i workspace 281.3G/44599183i | repeat-01 collected 26/26 workers (1105 items) tests 649 done 0 failed | 26 in flight, oldest 61s gw5 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
.......................................[contention-diag] +535s soak 28p/202t rss 9.4G pss 8.6G swap 0.0G majflt 201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.4G | host avail 25.3G/62.7G swapfree 44.5G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.9 cpu 15.65 | cgroup 8.9G/max oom_kill 0 | free scratch 280.9G/44598194i tmp 25.4G/976253i workspace 280.9G/44598194i | repeat-01 collected 26/26 workers (1105 items) tests 689 done 0 failed | 26 in flight, oldest 51s gw1 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
............[contention-diag] +550s soak 28p/210t rss 9.4G pss 8.6G swap 0.0G majflt 201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.4G | host avail 23.1G/62.7G swapfree 44.4G/64.0G oom_kill +0 | psi10 mem 0.49/0.49 io 1.31 cpu 13.98 | cgroup 8.9G/max oom_kill 0 | free scratch 280.8G/44597674i tmp 25.4G/976253i workspace 280.8G/44597674i | repeat-01 collected 26/26 workers (1105 items) tests 702 done 0 failed | 26 in flight, oldest 47s gw25 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
................[contention-diag] +566s soak 28p/218t rss 9.4G pss 8.6G swap 0.0G majflt 201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.4G | host avail 23.3G/62.7G swapfree 44.4G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 1.41 cpu 10.43 | cgroup 8.9G/max oom_kill 0 | free scratch 280.7G/44597220i tmp 25.4G/976253i workspace 280.7G/44597220i | repeat-01 collected 26/26 workers (1105 items) tests 718 done 0 failed | 26 in flight, oldest 62s gw25 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
.. [  6%]
...............[contention-diag] +581s soak 28p/198t rss 9.4G pss 8.6G swap 0.0G majflt 201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.4G | host avail 21.2G/62.7G swapfree 43.2G/64.0G oom_kill +0 | psi10 mem 4.44/3.32 io 5.73 cpu 16.88 | cgroup 8.9G/max oom_kill 0 | free scratch 280.0G/44567662i tmp 25.3G/975936i workspace 280.0G/44567662i | repeat-01 collected 26/26 workers (1105 items) tests 734 done 0 failed | 26 in flight, oldest 63s gw8 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_cycles_ranked_projects_and_survives_range_change
.........................................[contention-diag] +597s soak 28p/203t rss 9.2G pss 8.4G swap 0.3G majflt 1111 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.1G pss 8.3G | host avail 24.5G/62.7G swapfree 42.3G/64.0G oom_kill +0 | psi10 mem 8.49/6.37 io 11.94 cpu 11.87 | cgroup 8.6G/max oom_kill 0 | free scratch 279.5G/44566772i tmp 25.4G/976132i workspace 279.5G/44566772i | repeat-01 collected 26/26 workers (1105 items) tests 774 done 0 failed | 26 in flight, oldest 63s gw24 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
................ [  6%]
...............[contention-diag] +612s soak 28p/214t rss 9.2G pss 8.4G swap 0.3G majflt 2201 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.1G pss 8.3G | host avail 31.4G/62.7G swapfree 42.3G/64.0G oom_kill +0 | psi10 mem 5.42/1.28 io 2.57 cpu 15.04 | cgroup 8.6G/max oom_kill 0 | free scratch 279.9G/44566444i tmp 25.4G/976207i workspace 279.9G/44566444i | scratch used 0.0G in 7631 entries | repeat-01 collected 26/26 workers (1105 items) tests 805 done 0 failed | 26 in flight, oldest 70s gw1 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
.........................[contention-diag] +628s soak 28p/194t rss 9.3G pss 8.4G swap 0.2G majflt 2839 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.1G pss 8.3G | host avail 30.1G/62.7G swapfree 42.4G/64.0G oom_kill +0 | psi10 mem 2.89/0.31 io 0.91 cpu 13.2 | cgroup 8.7G/max oom_kill 0 | free scratch 279.8G/44565639i tmp 25.4G/976206i workspace 279.8G/44565639i | repeat-01 collected 26/26 workers (1105 items) tests 832 done 0 failed | 26 in flight, oldest 60s gw25 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
................................ [  6%]
.............................[contention-diag] +643s soak 31p/192t rss 9.3G pss 8.4G swap 0.2G majflt 2914 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.2G pss 8.3G, 3 descendant rss 0.0G pss 0.0G | host avail 30.5G/62.7G swapfree 42.4G/64.0G oom_kill +0 | psi10 mem 0.65/0.06 io 0.46 cpu 13.57 | cgroup 8.7G/max oom_kill 0 | free scratch 280.1G/44564952i tmp 25.4G/976224i workspace 280.1G/44564952i | repeat-01 collected 26/26 workers (1105 items) tests 892 done 0 failed | 26 in flight, oldest 46s gw24 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
.[contention-diag] +659s soak 29p/211t rss 9.3G pss 8.4G swap 0.2G majflt 2976 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.2G pss 8.3G, 1 descendant rss 0.0G pss 0.0G | host avail 30.7G/62.7G swapfree 42.4G/64.0G oom_kill +0 | psi10 mem 0.13/0.01 io 0.62 cpu 12.61 | cgroup 8.7G/max oom_kill 0 | free scratch 279.9G/44564665i tmp 25.4G/976223i workspace 279.9G/44564665i | repeat-01 collected 26/26 workers (1105 items) tests 894 done 0 failed | 26 in flight, oldest 62s gw24 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
....................[contention-diag] +674s soak 29p/193t rss 9.3G pss 8.4G swap 0.2G majflt 3026 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.2G pss 8.3G, 1 descendant rss 0.0G pss 0.0G | host avail 29.2G/62.7G swapfree 42.4G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.94 cpu 11.74 | cgroup 8.7G/max oom_kill 0 | free scratch 279.7G/44564104i tmp 25.4G/976225i workspace 279.7G/44564104i | repeat-01 collected 26/26 workers (1105 items) tests 913 done 0 failed | 26 in flight, oldest 54s gw3 tests/ace/tui/test_statistics_pane_filters.py::test_empty_project_filter_clears_to_all_projects_in_either_direction[P-core-Core]
...................... [  6%]
[contention-diag] +690s soak 29p/184t rss 9.3G pss 8.4G swap 0.2G majflt 3075 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.2G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 26.2G/62.7G swapfree 42.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.89 cpu 10.38 | cgroup 8.7G/max oom_kill 0 | free scratch 279.4G/44559617i tmp 25.4G/976225i workspace 279.4G/44559617i | repeat-01 collected 26/26 workers (1105 items) tests 934 done 0 failed | 26 in flight, oldest 63s gw13 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.........[contention-diag] +705s soak 30p/185t rss 9.3G pss 8.5G swap 0.2G majflt 3143 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.2G pss 8.4G, 2 descendant rss 0.0G pss 0.0G | host avail 25.9G/62.7G swapfree 42.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.66 cpu 9.98 | cgroup 8.8G/max oom_kill 0 | free scratch 279.2G/44562200i tmp 25.4G/976226i workspace 279.2G/44562200i | repeat-01 collected 26/26 workers (1105 items) tests 945 done 0 failed | 25 in flight, oldest 39s gw2 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
..........[contention-diag] +720s soak 30p/193t rss 9.4G pss 8.5G swap 0.2G majflt 3182 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.2G pss 8.4G, 2 descendant rss 0.0G pss 0.0G | host avail 24.7G/62.7G swapfree 42.4G/64.0G oom_kill +0 | psi10 mem 1.31/0.9 io 6.5 cpu 13.59 | cgroup 8.8G/max oom_kill 0 | free scratch 279.0G/44533478i tmp 25.3G/975868i workspace 279.0G/44533476i | repeat-01 collected 26/26 workers (1105 items) tests 955 done 0 failed | 26 in flight, oldest 48s gw0 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
................[contention-diag] +736s soak 31p/174t rss 9.4G pss 8.5G swap 0.3G majflt 3718 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.3G pss 8.4G, 3 descendant rss 0.0G pss 0.0G | host avail 23.1G/62.7G swapfree 41.4G/64.0G oom_kill +0 | psi10 mem 15.54/13.15 io 21.62 cpu 11.26 | cgroup 8.8G/max oom_kill 0 | free scratch 279.0G/44534432i tmp 25.3G/976055i workspace 279.0G/44534431i | scratch used 0.1G in 9363 entries | repeat-01 collected 26/26 workers (1105 items) tests 970 done 0 failed | 26 in flight, oldest 50s gw12 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
F[contention-failure] call tests/completion/test_update_refresh_soak.py::test_mixed_installed_and_absent_shells: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/test_mixed_installed_and_absen0')
capsys = <_pytest.capture.CaptureFixture object at 0x7fdfd6ffc050>

    def test_mixed_installed_and_absent_shells(
        tmp_path: Path,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        scripts = install_unmanaged_shells(tmp_path, shells=("bash", "zsh"))
        mark_scripts_stale(scripts)
        fish_script = unmanaged_script(tmp_path, "fish")
    
        payload = successful_update(tmp_path, capsys)
>       assert_unmanaged_refresh(scripts, payload)

tests/completion/test_update_refresh_soak.py:90: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

scripts = {'bash': PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/test_mixed_installed_and_absen0/complet...th('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/test_mixed_installed_and_absen0/completions/zsh/_sase')}
payload = {'changed': True, 'command': ['uv', 'tool', 'upgrade', '--color', 'never', 'sase'], 'completion_refresh': {'attempted'...ixed_installed_and_absen0/completions/zsh/_sase'}]}, 'counts': {'already_current': 1, 'removed': 0, 'updated': 2}, ...}

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
E           AssertionError: {'detail': 'zcompile timed out for /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/home-mvaj6co3/.sase/completion/grammar/78c7b8c18c448e5b584ced76/zsh/.stage.2868647/._sase.2868647.tmp', 'ok': False, 'shell': 'zsh', 'target': '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/test_mixed_installed_and_absen0/completions/zsh/_sase'}

tests/completion/_update_refresh_harness.py:125: AssertionError
.F.......[contention-diag] +751s soak 32p/184t rss 9.4G pss 8.5G swap 0.3G majflt 4571 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.3G pss 8.4G, 4 descendant rss 0.0G pss 0.0G | host avail 21.3G/62.7G swapfree 41.4G/64.0G oom_kill +0 | psi10 mem 6.35/3.23 io 5.59 cpu 11.58 | cgroup 8.8G/max oom_kill 0 | free scratch 278.8G/44532589i tmp 25.4G/976180i workspace 278.8G/44532589i | repeat-01 collected 26/26 workers (1105 items) tests 980 done 2 failed | 26 in flight, oldest 46s gw20 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_a_banner_toggles_it_like_enter
............[contention-diag] +766s soak 33p/185t rss 9.4G pss 8.5G swap 0.3G majflt 5068 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.3G pss 8.4G, 5 descendant rss 0.0G pss 0.0G | host avail 24.7G/62.7G swapfree 41.4G/64.0G oom_kill +0 | psi10 mem 3.59/0.65 io 1.31 cpu 15.29 | cgroup 8.9G/max oom_kill 0 | free scratch 278.4G/44532076i tmp 25.4G/976180i workspace 278.4G/44532076i | repeat-01 collected 26/26 workers (1105 items) tests 992 done 2 failed | 26 in flight, oldest 51s gw24 tests/completion/test_update_refresh_soak.py::test_mixed_installed_and_absent_shells
............... [  7%]
..........................................[contention-diag] +782s soak 36p/167t rss 9.5G pss 8.6G swap 0.3G majflt 5712 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.4G pss 8.5G, 8 descendant rss 0.0G pss 0.0G | host avail 22.1G/62.7G swapfree 41.4G/64.0G oom_kill +0 | psi10 mem 1.1/0.16 io 1.7 cpu 18.39 | cgroup 9.0G/max oom_kill 0 | free scratch 278.3G/44531760i tmp 25.4G/976189i workspace 278.3G/44531760i | repeat-01 collected 26/26 workers (1105 items) tests 1047 done 2 failed | 26 in flight, oldest 49s gw8 tests/ace/tui/test_statistics_pane_filters.py::test_custom_range_accepts_valid_input_and_rejects_invalid_input
.......................[contention-diag] +797s soak 30p/140t rss 9.5G pss 8.6G swap 0.3G majflt 6171 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.4G pss 8.5G, 2 descendant rss 0.0G pss 0.0G | host avail 18.7G/62.7G swapfree 41.2G/64.0G oom_kill +0 | psi10 mem 0.53/0.18 io 1.28 cpu 12.34 | cgroup 9.0G/max oom_kill 0 | free scratch 278.0G/44531574i tmp 25.4G/976200i workspace 278.0G/44531574i | repeat-01 collected 26/26 workers (1105 items) tests 1066 done 2 failed | 19 in flight, oldest 26s gw14 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
....... [  7%]
..[contention-diag] +812s soak 33p/137t rss 9.6G pss 8.6G swap 0.3G majflt 6238 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.4G pss 8.6G, 5 descendant rss 0.0G pss 0.0G | host avail 24.1G/62.7G swapfree 41.2G/64.0G oom_kill +0 | psi10 mem 0.1/0.03 io 1.25 cpu 10.58 | cgroup 9.0G/max oom_kill 0 | free scratch 277.2G/44531346i tmp 25.4G/976200i workspace 277.2G/44531346i | repeat-01 collected 26/26 workers (1105 items) tests 1079 done 2 failed | 13 in flight, oldest 42s gw14 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
...[contention-diag] +828s soak 30p/131t rss 9.5G pss 8.6G swap 0.3G majflt 6247 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.4G pss 8.6G, 2 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 41.3G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 2.0 cpu 13.72 | cgroup 9.0G/max oom_kill 0 | free scratch 275.9G/44531403i tmp 25.4G/976200i workspace 275.9G/44531403i | repeat-01 collected 26/26 workers (1105 items) tests 1084 done 2 failed | 10 in flight, oldest 57s gw14 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.........[contention-diag] +843s soak 32p/130t rss 9.6G pss 8.6G swap 0.3G majflt 6272 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.5G pss 8.6G, 4 descendant rss 0.0G pss 0.0G | host avail 21.6G/62.7G swapfree 41.1G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 1.76 cpu 14.76 | cgroup 9.0G/max oom_kill 0 | free scratch 275.3G/44531376i tmp 25.4G/976200i workspace 275.3G/44531376i | repeat-01 collected 26/26 workers (1105 items) tests 1093 done 2 failed | 7 in flight, oldest 64s gw0 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.........[contention-diag] +858s soak 29p/123t rss 9.6G pss 8.6G swap 0.3G majflt 6287 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 9.5G pss 8.6G, 1 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 41.1G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 0.46 cpu 8.61 | cgroup 9.0G/max oom_kill 0 | free scratch 275.6G/44531062i tmp 25.4G/976200i workspace 275.6G/44531062i | scratch used 0.2G in 10603 entries | repeat-01 collected 26/26 workers (1105 items) tests 1101 done 2 failed | 3 in flight, oldest 21s gw14 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
..                                                [  7%][contention-diag] +874s soak 28p/57t rss 2.3G pss 0.7G swap 0.2G majflt 6766 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.0G, 26 worker rss 2.2G pss 0.7G | host avail 24.7G/62.7G swapfree 41.1G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.95 cpu 11.7 | cgroup 8.4G/max oom_kill 0 | free scratch 275.1G/44530629i tmp 25.4G/976200i workspace 275.1G/44530629i | repeat-01 collected 26/26 workers (1105 items) tests 1105 done 2 failed


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________________ test_mixed_installed_and_absent_shells ____________________
[gw13] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/test_mixed_installed_and_absen0')
capsys = <_pytest.capture.CaptureFixture object at 0x7fdfd6ffc050>

    def test_mixed_installed_and_absent_shells(
        tmp_path: Path,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        scripts = install_unmanaged_shells(tmp_path, shells=("bash", "zsh"))
        mark_scripts_stale(scripts)
        fish_script = unmanaged_script(tmp_path, "fish")
    
        payload = successful_update(tmp_path, capsys)
>       assert_unmanaged_refresh(scripts, payload)

tests/completion/test_update_refresh_soak.py:90: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

scripts = {'bash': PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/test_mixed_installed_and_absen0/complet...th('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/test_mixed_installed_and_absen0/completions/zsh/_sase')}
payload = {'changed': True, 'command': ['uv', 'tool', 'upgrade', '--color', 'never', 'sase'], 'completion_refresh': {'attempted'...ixed_installed_and_absen0/completions/zsh/_sase'}]}, 'counts': {'already_current': 1, 'removed': 0, 'updated': 2}, ...}

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
E           AssertionError: {'detail': 'zcompile timed out for /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/home-mvaj6co3/.sase/completion/grammar/78c7b8c18c448e5b584ced76/zsh/.stage.2868647/._sase.2868647.tmp', 'ok': False, 'shell': 'zsh', 'target': '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw13/test_mixed_installed_and_absen0/completions/zsh/_sase'}

tests/completion/_update_refresh_harness.py:125: AssertionError
____________________ test_mixed_installed_and_absent_shells ____________________
[gw19] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw19/test_mixed_installed_and_absen0')
capsys = <_pytest.capture.CaptureFixture object at 0x7fef28a930e0>

    def test_mixed_installed_and_absent_shells(
        tmp_path: Path,
        capsys: pytest.CaptureFixture[str],
    ) -> None:
        scripts = install_unmanaged_shells(tmp_path, shells=("bash", "zsh"))
        mark_scripts_stale(scripts)
        fish_script = unmanaged_script(tmp_path, "fish")
    
        payload = successful_update(tmp_path, capsys)
        assert_unmanaged_refresh(scripts, payload)
        assert not fish_script.exists()
        assert read_stamp("fish") is None
        statuses = {row.shell: row for row in list_shell_statuses()}
        assert statuses["fish"].status == "not installed"
    
        second = successful_update(tmp_path, capsys)
>       assert_unmanaged_refresh(scripts, second)

tests/completion/test_update_refresh_soak.py:97: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

scripts = {'bash': PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw19/test_mixed_installed_and_absen0/complet...th('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw19/test_mixed_installed_and_absen0/completions/zsh/_sase')}
payload = {'changed': True, 'command': ['uv', 'tool', 'upgrade', '--color', 'never', 'sase'], 'completion_refresh': {'attempted'...ixed_installed_and_absen0/completions/zsh/_sase'}]}, 'counts': {'already_current': 1, 'removed': 0, 'updated': 2}, ...}

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
E           AssertionError: {'detail': 'zcompile timed out for /var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw19/home-xe2rm1qt/.sase/completion/grammar/78c7b8c18c448e5b584ced76/zsh/.stage.2869117/._sase.2869117.tmp', 'ok': False, 'shell': 'zsh', 'target': '/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-3/popen-gw19/test_mixed_installed_and_absen0/completions/zsh/_sase'}

tests/completion/_update_refresh_harness.py:125: AssertionError
============================= slowest 20 durations =============================
75.06s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
74.66s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
74.51s call     tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
74.32s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
73.75s call     tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
73.47s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
71.03s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
69.11s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
69.00s call     tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
68.37s call     tests/ace/tui/test_agent_archive_column_app.py::test_clicking_the_pulse_returns_to_the_inbox
68.19s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
67.35s call     tests/ace/tui/test_agent_archive_column_app.py::test_clicking_the_pulse_returns_to_the_inbox
66.98s call     tests/ace/tui/test_agent_archive_column_app.py::test_clicking_a_banner_toggles_it_like_enter
66.87s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
66.79s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
66.75s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
66.31s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
65.34s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
65.13s call     tests/ace/tui/test_agent_archive_column_app.py::test_clicking_the_pulse_returns_to_the_inbox
65.13s call     tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_cycles_ranked_projects_and_survives_range_change
=========================== short test summary info ============================
FAILED tests/completion/test_update_refresh_soak.py::test_mixed_installed_and_absent_shells
FAILED tests/completion/test_update_refresh_soak.py::test_mixed_installed_and_absent_shells
================== 2 failed, 1103 passed in 871.50s (0:14:31) ==================
[contention-diag] +879s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 209 | 1 parent rss 0.0G pss 0.0G | host avail 31.8G/62.7G swapfree 41.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.72 cpu 7.64 | cgroup 0.4G/max oom_kill 0 | free scratch 274.9G/44533642i tmp 25.4G/976200i workspace 274.9G/44533642i | repeat-01 collected 26/26 workers (1105 items) tests 1105 done 2 failed
[contention-diag] stopped (stopped by the harness) after 879s, 59 samples, 0 signal(s); peaks: cgroup_current 9.0G, min_free_scratch 274.9G, min_free_tmp 25.3G, min_free_workspace 274.9G, min_inodes_scratch 44530629, min_inodes_tmp 975868, min_inodes_workspace 44530629, min_mem_available 18.7G, min_swap_free 41.1G, oom_kill_delta 0, pressure_memory_full 13.15, pswpin_delta 347063, pswpout_delta 1554196, scratch_bytes 0.2G, soak_procs 36, soak_pss 8.6G, soak_rss 9.6G, soak_swap 0.3G, soak_threads 247

contention tally: 1 node(s) failed across 1 repeat(s) in 878.6s; red repeats: 1
  1/1  tests/completion/test_update_refresh_soak.py::test_mixed_installed_and_absent_shells  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics
error: recipe `test-contention` failed on line 779 with exit code 1
failed  exit=1  duration=881261ms

