# Chat History - ace-run (sase-1rq.2.1.4.1.5.3.1.2--mon-a)

- **TIMESTAMP:** 2026-11-09 14:58:12 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1rq.2.1.4.1.5.3.1.2--mon-a

## Prompt

sase monitor start --command 'set --; i=0; while [ "$i" -lt 13 ]; do set -- "$@" tests/ace/tui/test_config_transaction_widget.py tests/ace/tui/test_statistics_pane_filters.py tests/pager/test_app_dangling.py tests/completion/test_update_refresh_soak.py tests/test_output.py tests/ace/tui/test_agent_archive_column_app.py tests/ace/tui/modals/test_memory_panel.py tests/ace/tui/util/test_stall_watchdog_suspend.py tests/test_models_panel_usage_modal.py; i=$((i + 1)); done; set -- "$@" tests/completion/test_install.py; SASE_CONTENTION_CPUS=0,1 SASE_CONTENTION_WORKERS=26 SASE_CONTENTION_REPEAT=1 just test-contention -- --keep-duplicates "$@"' --reason 'Recheck prior contention failure families after separating zsh compilation timeout'

## Response

sase tool run fa9a547cbc819a6a3016ca23b20f1520
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
[contention-diag] root pid 4041490, sampler pid 4042281 on cpus 0-63 (soak cpus 0-1), python 3.14.7, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-3550990-1794253424228554323.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 35.3G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.37 cpu 0.02 | cgroup 0.2G/max oom_kill 0 | free scratch 275.4G/44473469i tmp 25.3G/976023i workspace 275.4G/44473470i | scratch used 0.1G in 7546 entries | progress none yet
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +16s soak 28p/80t rss 2.3G pss 2.0G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 2.1G pss 1.7G | host avail 36.2G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 7.62 | cgroup 2.2G/max oom_kill 0 | free scratch 275.8G/44475560i tmp 25.3G/976023i workspace 275.8G/44475560i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +32s soak 28p/80t rss 4.1G pss 3.6G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 3.9G pss 3.4G | host avail 34.0G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 13.49 | cgroup 3.8G/max oom_kill 0 | free scratch 275.8G/44475626i tmp 25.3G/976023i workspace 275.8G/44475626i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +47s soak 28p/80t rss 5.6G pss 5.0G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 5.3G pss 4.8G | host avail 33.3G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 17.15 | cgroup 5.2G/max oom_kill 0 | free scratch 275.6G/44475312i tmp 25.3G/976023i workspace 275.6G/44475312i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +62s soak 28p/80t rss 6.2G pss 5.6G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 5.9G pss 5.4G | host avail 34.9G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 18.83 | cgroup 5.8G/max oom_kill 0 | free scratch 275.5G/44475203i tmp 25.3G/976023i workspace 275.5G/44475203i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +77s soak 28p/80t rss 6.6G pss 6.1G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.4G pss 5.8G | host avail 36.3G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 17.04 | cgroup 6.3G/max oom_kill 0 | free scratch 275.2G/44465454i tmp 25.3G/976023i workspace 275.2G/44465454i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +92s soak 28p/80t rss 6.8G pss 6.2G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.5G pss 6.0G | host avail 32.4G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 1.2/1.07 io 7.01 cpu 13.87 | cgroup 6.4G/max oom_kill 0 | free scratch 275.0G/44447253i tmp 25.3G/975868i workspace 275.0G/44447253i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +108s soak 28p/80t rss 6.8G pss 6.3G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.6G pss 6.1G | host avail 37.4G/62.7G swapfree 43.6G/64.0G oom_kill +0 | psi10 mem 0.29/0.26 io 2.21 cpu 17.44 | cgroup 6.5G/max oom_kill 0 | free scratch 274.9G/44445175i tmp 25.3G/975975i workspace 274.9G/44445175i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +123s soak 28p/80t rss 7.1G pss 6.6G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.9G pss 6.3G | host avail 36.2G/62.7G swapfree 43.7G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.56 cpu 20.09 | cgroup 6.8G/max oom_kill 0 | free scratch 274.9G/44445014i tmp 25.3G/975974i workspace 274.9G/44445014i | scratch used 0.1G in 7575 entries | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +138s soak 28p/80t rss 7.5G pss 7.0G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.3G pss 6.8G | host avail 35.2G/62.7G swapfree 43.7G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.13 cpu 20.31 | cgroup 7.2G/max oom_kill 0 | free scratch 274.9G/44445023i tmp 25.3G/975972i workspace 274.9G/44445023i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +153s soak 28p/80t rss 7.7G pss 7.1G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.4G pss 6.9G | host avail 36.2G/62.7G swapfree 43.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.33 cpu 14.4 | cgroup 7.3G/max oom_kill 0 | free scratch 274.7G/44444925i tmp 25.3G/975992i workspace 274.7G/44444925i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +169s soak 28p/80t rss 7.7G pss 7.1G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.4G pss 6.9G | host avail 34.8G/62.7G swapfree 45.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.59 cpu 15.1 | cgroup 7.3G/max oom_kill 0 | free scratch 280.7G/44508133i tmp 25.3G/975993i workspace 280.7G/44508133i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +184s soak 28p/80t rss 7.7G pss 7.2G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.5G pss 7.0G | host avail 34.6G/62.7G swapfree 45.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 17.44 | cgroup 7.4G/max oom_kill 0 | free scratch 280.6G/44507621i tmp 25.3G/975993i workspace 280.6G/44507621i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +199s soak 28p/80t rss 8.0G pss 7.4G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.7G pss 7.2G | host avail 34.0G/62.7G swapfree 45.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 16.49 | cgroup 7.6G/max oom_kill 0 | free scratch 280.5G/44507275i tmp 25.3G/975993i workspace 280.5G/44507275i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +214s soak 28p/80t rss 8.0G pss 7.5G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.8G pss 7.3G | host avail 33.7G/62.7G swapfree 45.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 15.8 | cgroup 7.7G/max oom_kill 0 | free scratch 280.5G/44506989i tmp 25.3G/975993i workspace 280.5G/44506989i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +230s soak 28p/80t rss 8.1G pss 7.5G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.8G pss 7.3G | host avail 30.2G/62.7G swapfree 45.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 17.91 | cgroup 7.7G/max oom_kill 0 | free scratch 280.4G/44506925i tmp 25.3G/975993i workspace 280.4G/44506925i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +245s soak 28p/80t rss 8.3G pss 7.7G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.0G pss 7.5G | host avail 27.9G/62.7G swapfree 45.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.46 | cgroup 7.9G/max oom_kill 0 | free scratch 280.2G/44506935i tmp 25.3G/975993i workspace 280.2G/44506935i | scratch used 0.1G in 7575 entries | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +260s soak 28p/80t rss 8.6G pss 8.0G swap 0.0G majflt 5 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.3G pss 7.8G | host avail 28.1G/62.7G swapfree 45.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.31 | cgroup 8.2G/max oom_kill 0 | free scratch 280.1G/44506908i tmp 25.3G/975993i workspace 280.1G/44506908i | repeat-01 collected 21/26 workers (1130 items) tests 0 done 0 failed
26 workers [1130 items]

........................................................................ [  4%]
........................................[contention-diag] +276s soak 29p/147t rss 8.9G pss 8.2G swap 0.0G majflt 9 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.6G pss 8.0G, 1 descendant rss 0.0G pss 0.0G | host avail 25.6G/62.7G swapfree 45.7G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 20.02 | cgroup 8.4G/max oom_kill 0 | free scratch 280.0G/44505803i tmp 25.3G/975993i workspace 280.0G/44505803i | repeat-01 collected 26/26 workers (1130 items) tests 111 done 0 failed | 26 in flight, oldest 14s gw6 tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
................................ [  5%]
........................................................................ [  6%]
...................................[contention-diag] +291s soak 29p/146t rss 8.9G pss 8.3G swap 0.0G majflt 20 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.7G pss 8.0G, 1 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.06 cpu 16.55 | cgroup 8.4G/max oom_kill 0 | free scratch 279.7G/44505341i tmp 25.3G/975993i workspace 279.7G/44505341i | repeat-01 collected 26/26 workers (1130 items) tests 241 done 0 failed | 26 in flight, oldest 29s gw6 tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
..................................... [  6%]
........................................................................ [  7%]
......................................................[contention-diag] +306s soak 28p/176t rss 9.1G pss 8.3G swap 0.0G majflt 97 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.8G pss 8.1G | host avail 25.4G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 16.67 | cgroup 8.5G/max oom_kill 0 | free scratch 280.3G/44504457i tmp 25.3G/975993i workspace 280.3G/44504457i | repeat-01 collected 26/26 workers (1130 items) tests 405 done 0 failed | 26 in flight, oldest 44s gw6 tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
.................. [  7%]
..................................................................[contention-diag] +321s soak 28p/166t rss 9.1G pss 8.4G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.9G pss 8.1G | host avail 26.0G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.41 | cgroup 8.6G/max oom_kill 0 | free scratch 280.0G/44504092i tmp 25.3G/975993i workspace 280.0G/44504092i | repeat-01 collected 26/26 workers (1130 items) tests 493 done 0 failed | 26 in flight, oldest 60s gw12 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
...... [  8%]
.............[contention-diag] +337s soak 28p/196t rss 9.2G pss 8.4G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.9G pss 8.2G | host avail 30.4G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.22 | cgroup 8.6G/max oom_kill 0 | free scratch 279.8G/44503839i tmp 25.3G/975993i workspace 279.8G/44503839i | repeat-01 collected 26/26 workers (1130 items) tests 517 done 0 failed | 26 in flight, oldest 72s gw15 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.............[contention-diag] +352s soak 28p/213t rss 9.2G pss 8.4G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.0G pss 8.2G | host avail 29.4G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.21/0.21 io 0.33 cpu 17.69 | cgroup 8.7G/max oom_kill 0 | free scratch 279.6G/44503677i tmp 25.3G/975993i workspace 279.6G/44503677i | repeat-01 collected 26/26 workers (1130 items) tests 529 done 0 failed | 26 in flight, oldest 48s gw13 tests/ace/tui/test_config_transaction_widget.py::test_apply_conflict_preserves_draft_and_returns_to_replan
...........[contention-diag] +367s soak 28p/201t rss 9.3G pss 8.5G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.0G pss 8.2G | host avail 28.4G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.06 cpu 21.24 | cgroup 8.7G/max oom_kill 0 | free scratch 280.0G/44503493i tmp 25.3G/975993i workspace 280.0G/44503493i | scratch used 0.2G in 10169 entries | repeat-01 collected 26/26 workers (1130 items) tests 541 done 0 failed | 26 in flight, oldest 49s gw24 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
...........[contention-diag] +383s soak 28p/212t rss 9.3G pss 8.5G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 31.1G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 23.93 | cgroup 8.8G/max oom_kill 0 | free scratch 280.3G/44503324i tmp 25.3G/975993i workspace 280.3G/44503324i | repeat-01 collected 26/26 workers (1130 items) tests 552 done 0 failed | 26 in flight, oldest 58s gw23 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
........[contention-diag] +398s soak 28p/212t rss 9.4G pss 8.5G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 29.4G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 20.24 | cgroup 8.8G/max oom_kill 0 | free scratch 280.3G/44503209i tmp 25.3G/975993i workspace 280.3G/44503209i | repeat-01 collected 26/26 workers (1130 items) tests 560 done 0 failed | 26 in flight, oldest 51s gw6 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
................ [  9%]
.........F[contention-failure] call tests/test_output.py::test_provider_timer_thread_survives_live_update_errors: def test_provider_timer_thread_survives_live_update_errors() -> None:
        """A Live.update exception must not kill the named timer thread."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        with (
            patch("sase.output._PROVIDER_TIMER_INTERVAL_SECONDS", 0.01),
            patch.object(Live, "update", side_effect=RuntimeError("display boom")),
            patch("sase.output._PROVIDER_TIMER_COMPLETION_DISPLAY_SECONDS", 0),
            provider_timer("Short operation"),
        ):
>           timer_thread = _wait_for_provider_timer_thread(existing_thread_ids)
                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_output.py:124: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {139797205464768, 139797618014080}

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
...[contention-diag] +413s soak 28p/200t rss 9.4G pss 8.5G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 27.3G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.55 | cgroup 8.8G/max oom_kill 0 | free scratch 280.2G/44502970i tmp 25.3G/975993i workspace 280.2G/44502970i | repeat-01 collected 26/26 workers (1130 items) tests 586 done 1 failed | 26 in flight, oldest 49s gw1 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
................[contention-diag] +429s soak 29p/206t rss 9.4G pss 8.6G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G, 1 descendant rss 0.0G pss 0.0G | host avail 24.7G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.71 | cgroup 8.8G/max oom_kill 0 | free scratch 280.2G/44502818i tmp 25.3G/975993i workspace 280.2G/44502818i | repeat-01 collected 26/26 workers (1130 items) tests 605 done 1 failed | 26 in flight, oldest 59s gw14 tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
.......[contention-diag] +444s soak 28p/206t rss 9.4G pss 8.6G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.1G pss 8.3G | host avail 25.0G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.68 | cgroup 8.8G/max oom_kill 0 | free scratch 279.7G/44502688i tmp 25.3G/975993i workspace 279.7G/44502688i | repeat-01 collected 26/26 workers (1130 items) tests 612 done 1 failed | 26 in flight, oldest 75s gw14 tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
..............................[contention-diag] +459s soak 28p/202t rss 9.4G pss 8.6G swap 0.0G majflt 100 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.3G | host avail 27.0G/62.7G swapfree 45.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.78 | cgroup 8.8G/max oom_kill 0 | free scratch 279.2G/44502340i tmp 25.3G/975993i workspace 279.2G/44502340i | repeat-01 collected 26/26 workers (1130 items) tests 636 done 1 failed | 26 in flight, oldest 90s gw14 tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
...... [  9%]
......................F[contention-failure] call tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-4/popen-gw14/test_plan_worker_is_cancelled_0')

    async def test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount(
        tmp_path: Path,
    ) -> None:
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
        entered = Event()
        release = Event()
        original = cem.plan_config_edit
    
        def blocked(*args: object, **kwargs: object) -> object:
            entered.set()
            release.wait(timeout=5)
            return original(*args, **kwargs)
    
        async with AcePage() as page:
            modal = ConfigEditModal(view, field=view.fields_by_path["timezone"])
            await open_config_edit_modal(page, modal)
            modal.query_one("#config-edit-input", SingleLineVimTextArea).text = "UTC"
            with patch.object(cem, "plan_config_edit", side_effect=blocked):
                modal.action_confirm()
                await page.wait_for(lambda _screen: entered.is_set())
                worker = modal._plan_worker
                assert worker is not None
                modal.dismiss(None)
                await page.expect_no_modal()
>               await page.wait_for(lambda _screen: worker.is_cancelled)

tests/ace/tui/test_config_transaction_widget.py:73: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:577: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f6ad9725d20>

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
..[contention-diag] +475s soak 29p/209t rss 9.4G pss 8.6G swap 0.0G majflt 101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 23.5G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 13.26 | cgroup 8.9G/max oom_kill 0 | free scratch 279.0G/44499497i tmp 25.3G/975993i workspace 279.0G/44499497i | repeat-01 collected 26/26 workers (1130 items) tests 673 done 2 failed | 26 in flight, oldest 67s gw9 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
........[contention-diag] +490s soak 29p/209t rss 9.4G pss 8.6G swap 0.0G majflt 101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 12.13 | cgroup 8.9G/max oom_kill 0 | free scratch 279.0G/44500737i tmp 25.3G/975993i workspace 279.0G/44500737i | scratch used 0.2G in 11502 entries | repeat-01 collected 26/26 workers (1130 items) tests 680 done 2 failed | 26 in flight, oldest 56s gw11 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
.......[contention-diag] +505s soak 29p/220t rss 9.5G pss 8.6G swap 0.0G majflt 101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 31.2G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 10.64 | cgroup 8.9G/max oom_kill 0 | free scratch 279.3G/44499646i tmp 25.3G/975993i workspace 279.3G/44499646i | repeat-01 collected 26/26 workers (1130 items) tests 688 done 2 failed | 26 in flight, oldest 63s gw0 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
..................[contention-diag] +521s soak 29p/206t rss 9.5G pss 8.6G swap 0.0G majflt 101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 30.8G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 15.43 | cgroup 8.9G/max oom_kill 0 | free scratch 279.4G/44489032i tmp 25.3G/975993i workspace 279.4G/44489031i | repeat-01 collected 26/26 workers (1130 items) tests 706 done 2 failed | 26 in flight, oldest 65s gw17 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.............. [  9%]
.[contention-diag] +536s soak 29p/212t rss 9.5G pss 8.6G swap 0.0G majflt 101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 24.2G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 8.55 cpu 13.7 | cgroup 8.9G/max oom_kill 0 | free scratch 279.2G/44473123i tmp 25.3G/975776i workspace 279.2G/44473123i | repeat-01 collected 26/26 workers (1130 items) tests 721 done 2 failed | 26 in flight, oldest 80s gw17 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
......[contention-diag] +552s soak 28p/220t rss 9.5G pss 8.6G swap 0.0G majflt 101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G | host avail 32.6G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 2.75 cpu 15.5 | cgroup 8.9G/max oom_kill 0 | free scratch 279.0G/44470419i tmp 25.3G/975939i workspace 279.0G/44470419i | repeat-01 collected 26/26 workers (1130 items) tests 727 done 2 failed | 26 in flight, oldest 67s gw4 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
....[contention-diag] +567s soak 29p/229t rss 9.5G pss 8.6G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 11.3 cpu 14.52 | cgroup 8.9G/max oom_kill 0 | free scratch 278.7G/44440607i tmp 25.3G/975609i workspace 278.7G/44440607i | repeat-01 collected 26/26 workers (1130 items) tests 731 done 2 failed | 26 in flight, oldest 66s gw8 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
......................................[contention-diag] +582s soak 30p/195t rss 9.5G pss 8.6G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G, 2 descendant rss 0.0G pss 0.0G | host avail 33.5G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 14.93 cpu 10.37 | cgroup 8.9G/max oom_kill 0 | free scratch 278.5G/44438024i tmp 25.3G/975877i workspace 278.5G/44438024i | repeat-01 collected 26/26 workers (1130 items) tests 768 done 2 failed | 26 in flight, oldest 76s gw2 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
........[contention-diag] +598s soak 28p/198t rss 9.5G pss 8.6G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G | host avail 33.7G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.79 cpu 17.54 | cgroup 8.9G/max oom_kill 0 | free scratch 278.5G/44439462i tmp 25.3G/975919i workspace 278.5G/44439462i | repeat-01 collected 26/26 workers (1130 items) tests 776 done 2 failed | 26 in flight, oldest 66s gw19 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
............... [  9%]
....[contention-diag] +613s soak 29p/218t rss 9.5G pss 8.7G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.3G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 35.8G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.89 cpu 19.32 | cgroup 8.9G/max oom_kill 0 | free scratch 278.5G/44439038i tmp 25.3G/975921i workspace 278.5G/44439038i | scratch used 0.2G in 12647 entries | repeat-01 collected 26/26 workers (1130 items) tests 794 done 2 failed | 26 in flight, oldest 60s gw4 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_the_pulse_returns_to_the_inbox
...........................................[contention-diag] +628s soak 29p/190t rss 9.5G pss 8.7G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.3G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 35.1G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 23.16 | cgroup 9.0G/max oom_kill 0 | free scratch 278.5G/44439090i tmp 25.3G/975930i workspace 278.5G/44439090i | repeat-01 collected 26/26 workers (1130 items) tests 831 done 2 failed | 25 in flight, oldest 58s gw8 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
......................... [  9%]
..[contention-diag] +643s soak 30p/188t rss 9.6G pss 8.7G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.3G pss 8.4G, 2 descendant rss 0.0G pss 0.0G | host avail 33.0G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.34 cpu 16.85 | cgroup 9.0G/max oom_kill 0 | free scratch 278.5G/44439050i tmp 25.3G/975941i workspace 278.5G/44439050i | repeat-01 collected 26/26 workers (1130 items) tests 863 done 2 failed | 26 in flight, oldest 65s gw12 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
....................[contention-diag] +659s soak 29p/204t rss 9.6G pss 8.7G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.3G pss 8.4G, 1 descendant rss 0.0G pss 0.0G | host avail 33.9G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 22.57 | cgroup 9.0G/max oom_kill 0 | free scratch 278.5G/44438842i tmp 25.3G/975941i workspace 278.5G/44438842i | repeat-01 collected 26/26 workers (1130 items) tests 885 done 2 failed | 26 in flight, oldest 57s gw19 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_the_pulse_returns_to_the_inbox
......................[contention-diag] +674s soak 28p/196t rss 9.6G pss 8.7G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.3G pss 8.4G | host avail 35.8G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.19/0.19 io 0.24 cpu 35.55 | cgroup 9.0G/max oom_kill 0 | free scratch 278.5G/44438523i tmp 25.3G/975941i workspace 278.5G/44438523i | repeat-01 collected 26/26 workers (1130 items) tests 902 done 2 failed | 26 in flight, oldest 50s gw0 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
............................ [  9%]
....[contention-diag] +689s soak 29p/201t rss 9.6G pss 8.7G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.3G pss 8.5G, 1 descendant rss 0.0G pss 0.0G | host avail 35.2G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.05 cpu 29.3 | cgroup 9.0G/max oom_kill 0 | free scratch 278.5G/44438266i tmp 25.3G/975941i workspace 278.5G/44438266i | repeat-01 collected 26/26 workers (1130 items) tests 940 done 2 failed | 25 in flight, oldest 60s gw14 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
........................................[contention-diag] +705s soak 31p/194t rss 9.6G pss 8.7G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.3G pss 8.5G, 3 descendant rss 0.0G pss 0.0G | host avail 31.5G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 23.45 | cgroup 9.1G/max oom_kill 0 | free scratch 279.0G/44437988i tmp 25.3G/975941i workspace 279.0G/44437988i | repeat-01 collected 26/26 workers (1130 items) tests 977 done 2 failed | 26 in flight, oldest 45s gw19 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_a_banner_toggles_it_like_enter
............................ [  9%]
[contention-diag] +720s soak 32p/188t rss 9.6G pss 8.8G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.4G pss 8.5G, 4 descendant rss 0.0G pss 0.0G | host avail 29.0G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.47 | cgroup 9.1G/max oom_kill 0 | free scratch 278.8G/44437742i tmp 25.3G/975941i workspace 278.8G/44437742i | repeat-01 collected 26/26 workers (1130 items) tests 1004 done 2 failed | 25 in flight, oldest 47s gw10 tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
..................................[contention-diag] +735s soak 31p/195t rss 9.7G pss 8.8G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.4G pss 8.5G, 3 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.04 | cgroup 9.1G/max oom_kill 0 | free scratch 278.7G/44437419i tmp 25.3G/975941i workspace 278.7G/44437419i | scratch used 0.3G in 14621 entries | repeat-01 collected 26/26 workers (1130 items) tests 1041 done 2 failed | 26 in flight, oldest 54s gw1 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
..................[contention-diag] +750s soak 30p/175t rss 9.7G pss 8.8G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.4G pss 8.6G, 2 descendant rss 0.0G pss 0.0G | host avail 28.0G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.64 | cgroup 9.2G/max oom_kill 0 | free scratch 278.6G/44437210i tmp 25.3G/975941i workspace 278.6G/44437210i | repeat-01 collected 26/26 workers (1130 items) tests 1059 done 2 failed | 26 in flight, oldest 45s gw13 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
..........[contention-diag] +766s soak 29p/178t rss 9.7G pss 8.8G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.4G pss 8.6G, 1 descendant rss 0.0G pss 0.0G | host avail 29.7G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.21 | cgroup 9.2G/max oom_kill 0 | free scratch 278.8G/44437002i tmp 25.3G/975941i workspace 278.8G/44437002i | repeat-01 collected 26/26 workers (1130 items) tests 1070 done 2 failed | 26 in flight, oldest 56s gw21 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.........[contention-diag] +781s soak 29p/193t rss 9.7G pss 8.8G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.5G pss 8.6G, 1 descendant rss 0.0G pss 0.0G | host avail 25.6G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.35 | cgroup 9.2G/max oom_kill 0 | free scratch 278.8G/44436877i tmp 25.3G/975941i workspace 278.8G/44436877i | repeat-01 collected 26/26 workers (1130 items) tests 1077 done 2 failed | 23 in flight, oldest 62s gw9 tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
. [  9%]
.........................[contention-diag] +796s soak 31p/165t rss 9.8G pss 8.9G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.5G pss 8.6G, 3 descendant rss 0.0G pss 0.0G | host avail 26.2G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.59 | cgroup 9.2G/max oom_kill 0 | free scratch 278.5G/44436819i tmp 25.3G/975941i workspace 278.5G/44436819i | repeat-01 collected 26/26 workers (1130 items) tests 1104 done 2 failed | 18 in flight, oldest 73s gw25 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.........[contention-diag] +812s soak 28p/156t rss 9.8G pss 8.9G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.5G pss 8.6G | host avail 29.9G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.61 | cgroup 9.3G/max oom_kill 0 | free scratch 278.8G/44436745i tmp 25.3G/975941i workspace 278.8G/44436745i | repeat-01 collected 26/26 workers (1130 items) tests 1112 done 2 failed | 14 in flight, oldest 39s gw17 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_a_banner_toggles_it_like_enter
......[contention-diag] +827s soak 30p/155t rss 9.8G pss 8.9G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.5G pss 8.6G, 2 descendant rss 0.0G pss 0.0G | host avail 26.1G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.78 | cgroup 9.3G/max oom_kill 0 | free scratch 280.1G/44438562i tmp 25.3G/975940i workspace 280.1G/44438562i | repeat-01 collected 26/26 workers (1130 items) tests 1119 done 2 failed | 10 in flight, oldest 45s gw9 tests/ace/tui/test_agent_archive_column_app.py::test_clicking_the_pulse_returns_to_the_inbox
..........                       [  9%][contention-diag] +842s soak 28p/119t rss 9.8G pss 8.9G swap 0.0G majflt 102 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.5G pss 8.6G | host avail 25.5G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 13.41 | cgroup 9.3G/max oom_kill 0 | free scratch 279.8G/44438705i tmp 25.3G/975940i workspace 279.8G/44438705i | repeat-01 collected 26/26 workers (1130 items) tests 1130 done 2 failed


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________ test_provider_timer_thread_survives_live_update_errors ____________
[gw19] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_provider_timer_thread_survives_live_update_errors() -> None:
        """A Live.update exception must not kill the named timer thread."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        with (
            patch("sase.output._PROVIDER_TIMER_INTERVAL_SECONDS", 0.01),
            patch.object(Live, "update", side_effect=RuntimeError("display boom")),
            patch("sase.output._PROVIDER_TIMER_COMPLETION_DISPLAY_SECONDS", 0),
            provider_timer("Short operation"),
        ):
>           timer_thread = _wait_for_provider_timer_thread(existing_thread_ids)
                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_output.py:124: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {139797205464768, 139797618014080}

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
⏱️  Short operation [00:00]
_______ test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount _______
[gw14] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-4/popen-gw14/test_plan_worker_is_cancelled_0')

    async def test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount(
        tmp_path: Path,
    ) -> None:
        view, _ = config_edit_view(tmp_path, {"timezone": "US/Pacific"})
        entered = Event()
        release = Event()
        original = cem.plan_config_edit
    
        def blocked(*args: object, **kwargs: object) -> object:
            entered.set()
            release.wait(timeout=5)
            return original(*args, **kwargs)
    
        async with AcePage() as page:
            modal = ConfigEditModal(view, field=view.fields_by_path["timezone"])
            await open_config_edit_modal(page, modal)
            modal.query_one("#config-edit-input", SingleLineVimTextArea).text = "UTC"
            with patch.object(cem, "plan_config_edit", side_effect=blocked):
                modal.action_confirm()
                await page.wait_for(lambda _screen: entered.is_set())
                worker = modal._plan_worker
                assert worker is not None
                modal.dismiss(None)
                await page.expect_no_modal()
>               await page.wait_for(lambda _screen: worker.is_cancelled)

tests/ace/tui/test_config_transaction_widget.py:73: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:577: in wait_for
    await _poll_until(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

predicate = <function AcePage.wait_for.<locals>.<lambda> at 0x7f6ad9725d20>

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
============================= slowest 20 durations =============================
97.40s call     tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
91.21s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
89.87s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
79.04s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
76.59s call     tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
75.43s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
75.32s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
72.43s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
72.28s call     tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
71.84s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
71.38s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
69.98s call     tests/ace/tui/test_agent_archive_column_app.py::test_archive_replaces_the_inbox_column_and_keys_navigate_it
69.93s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
69.92s call     tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
69.35s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
69.27s call     tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
68.84s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
68.69s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
68.59s call     tests/ace/tui/test_agent_archive_column_app.py::test_J_switches_to_the_pulse_and_enter_returns_to_the_inbox
68.32s call     tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
=========================== short test summary info ============================
FAILED tests/test_output.py::test_provider_timer_thread_survives_live_update_errors
FAILED tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount
================== 2 failed, 1128 passed in 848.10s (0:14:08) ==================
[contention-diag] +856s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G | host avail 36.8G/62.7G swapfree 45.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 13.18 | cgroup 0.4G/max oom_kill 0 | free scratch 279.7G/44446262i tmp 25.3G/975940i workspace 279.7G/44446262i | scratch used 0.1G in 7646 entries | repeat-01 collected 26/26 workers (1130 items) tests 1130 done 2 failed | 5 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 856s, 57 samples, 0 signal(s); peaks: cgroup_current 9.3G, min_free_scratch 274.7G, min_free_tmp 25.3G, min_free_workspace 274.7G, min_inodes_scratch 44436745, min_inodes_tmp 975609, min_inodes_workspace 44436745, min_mem_available 23.3G, min_swap_free 43.6G, oom_kill_delta 0, pressure_memory_full 1.07, pswpin_delta 124299, pswpout_delta 207335, scratch_bytes 0.3G, soak_procs 32, soak_pss 8.9G, soak_rss 9.8G, soak_swap 0.0G, soak_threads 229

contention tally: 2 node(s) failed across 1 repeat(s) in 855.7s; red repeats: 1
  1/1  tests/ace/tui/test_config_transaction_widget.py::test_plan_worker_is_cancelled_and_late_result_ignored_on_unmount  (repeats 1)
  1/1  tests/test_output.py::test_provider_timer_thread_survives_live_update_errors  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics
error: recipe `test-contention` failed on line 779 with exit code 1
failed  exit=1  duration=858184ms

