# Chat History - ace-run (sase-1rq.2.1.4.1.5.3.1.2--mon-4)

- **TIMESTAMP:** 2026-11-09 11:09:22 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** sase-1rq.2.1.4.1.5.3.1.2--mon-4

## Prompt

sase monitor start --command 'set --; i=0; while [ "$i" -lt 13 ]; do set -- "$@" tests/ace/tui/test_statistics_pane_filters.py tests/pager/test_app_dangling.py tests/completion/test_update_refresh_soak.py tests/test_output.py; i=$((i + 1)); done; SASE_CONTENTION_CPUS=0,1 SASE_CONTENTION_WORKERS=26 SASE_CONTENTION_REPEAT=1 just test-contention -- --keep-duplicates "$@"' --reason 'Repeat the four full-run failure families under 26 workers pinned to CPUs 0-1'

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
contention soak: 1 repeat(s), 26 workers, dist=worksteal

---------- contention repeat 1/1 ----------
[contention-diag] root pid 27460, sampler pid 27526 on cpus 0-63 (soak cpus 0-1), python 3.14.7, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-4069011-1794240039669336154.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 39.2G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 303.6G/44894182i tmp 26.1G/985690i workspace 303.6G/44894182i | scratch used 0.3G in 55280 entries (truncated) | progress none yet
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +17s soak 28p/80t rss 2.8G pss 2.4G swap 0.0G majflt 7 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 2.6G pss 2.2G | host avail 39.0G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 13.52 | cgroup 2.6G/max oom_kill 0 | free scratch 303.6G/44894048i tmp 26.1G/985690i workspace 303.6G/44894048i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +32s soak 28p/80t rss 4.7G pss 4.2G swap 0.0G majflt 7 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 4.5G pss 4.0G | host avail 37.2G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.86 cpu 18.28 | cgroup 4.3G/max oom_kill 0 | free scratch 303.6G/44894046i tmp 26.1G/985690i workspace 303.6G/44894046i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +47s soak 28p/80t rss 5.9G pss 5.3G swap 0.0G majflt 7 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 5.6G pss 5.1G | host avail 36.1G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.69 cpu 18.06 | cgroup 5.4G/max oom_kill 0 | free scratch 303.6G/44893745i tmp 26.1G/985690i workspace 303.6G/44893745i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +63s soak 28p/80t rss 6.3G pss 5.8G swap 0.0G majflt 7 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.1G pss 5.5G | host avail 34.3G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 15.71 | cgroup 5.9G/max oom_kill 0 | free scratch 303.5G/44893576i tmp 26.1G/985690i workspace 303.5G/44893576i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +78s soak 28p/80t rss 6.7G pss 6.2G swap 0.0G majflt 7 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.5G pss 6.0G | host avail 32.9G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 13.87 | cgroup 6.3G/max oom_kill 0 | free scratch 303.4G/44893424i tmp 26.1G/985685i workspace 303.4G/44893424i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +93s soak 28p/80t rss 6.8G pss 6.3G swap 0.0G majflt 7 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.6G pss 6.1G | host avail 35.2G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 13.65 | cgroup 6.4G/max oom_kill 0 | free scratch 302.8G/44890916i tmp 26.1G/985690i workspace 302.8G/44890916i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +108s soak 28p/80t rss 6.9G pss 6.4G swap 0.0G majflt 7 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 6.7G pss 6.2G | host avail 35.2G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.8 | cgroup 6.5G/max oom_kill 0 | free scratch 302.8G/44890945i tmp 26.1G/985690i workspace 302.8G/44890945i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +123s soak 28p/80t rss 7.4G pss 6.8G swap 0.0G majflt 7 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.1G pss 6.6G | host avail 36.3G/62.7G swapfree 47.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.82 | cgroup 7.0G/max oom_kill 0 | free scratch 303.2G/44894534i tmp 26.1G/985688i workspace 303.2G/44894534i | scratch used 0.4G in 81911 entries (truncated) | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
26 workers [455 items]

...........................................[contention-diag] +141s soak 28p/119t rss 7.9G pss 7.2G swap 0.0G majflt 8 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.7G pss 7.0G | host avail 36.5G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 17.25 | cgroup 7.4G/max oom_kill 0 | free scratch 303.2G/44893764i tmp 26.1G/985687i workspace 303.2G/44893764i | repeat-01 collected 26/26 workers (455 items) tests 43 done 0 failed | 26 in flight, oldest 6s gw2 tests/completion/test_update_refresh_soak.py::test_chezmoi_managed_scripts_are_refreshed_with_preserved_owner
......[contention-diag] +156s soak 32p/151t rss 8.0G pss 7.3G swap 0.0G majflt 8 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.8G pss 7.1G, 4 descendant rss 0.0G pss 0.0G | host avail 34.8G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 12.59 | cgroup 7.5G/max oom_kill 0 | free scratch 303.1G/44893323i tmp 26.1G/985689i workspace 303.1G/44893323i | repeat-01 collected 26/26 workers (455 items) tests 44 done 0 failed | 26 in flight, oldest 21s gw2 tests/completion/test_update_refresh_soak.py::test_chezmoi_managed_scripts_are_refreshed_with_preserved_owner
.............[contention-diag] +171s soak 28p/173t rss 8.1G pss 7.3G swap 0.0G majflt 10 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 7.8G pss 7.1G | host avail 37.6G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.62 | cgroup 7.5G/max oom_kill 0 | free scratch 302.9G/44893089i tmp 26.1G/985689i workspace 302.9G/44893089i | repeat-01 collected 26/26 workers (455 items) tests 62 done 0 failed | 26 in flight, oldest 36s gw0 tests/ace/tui/test_statistics_pane_filters.py::test_range_and_project_group_switches_coalesce_to_latest_selection
.......... [  3%]
..........................................................[contention-diag] +186s soak 33p/152t rss 8.3G pss 7.6G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.1G pss 7.3G, 5 descendant rss 0.0G pss 0.0G | host avail 36.2G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.64 | cgroup 7.8G/max oom_kill 0 | free scratch 302.9G/44892737i tmp 26.1G/985689i workspace 302.9G/44892737i | repeat-01 collected 26/26 workers (455 items) tests 127 done 0 failed | 26 in flight, oldest 52s gw10 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.............. [  5%]
......................[contention-diag] +202s soak 31p/160t rss 8.5G pss 7.8G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.3G pss 7.6G, 3 descendant rss 0.0G pss 0.0G | host avail 33.8G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.67 | cgroup 8.0G/max oom_kill 0 | free scratch 303.0G/44892505i tmp 26.1G/985689i workspace 303.0G/44892505i | repeat-01 collected 26/26 workers (455 items) tests 159 done 0 failed | 25 in flight, oldest 67s gw10 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.........[contention-diag] +217s soak 32p/179t rss 8.9G pss 8.1G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.6G pss 7.9G, 4 descendant rss 0.0G pss 0.0G | host avail 35.2G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 20.16 | cgroup 8.4G/max oom_kill 0 | free scratch 302.9G/44892235i tmp 26.1G/985689i workspace 302.9G/44892235i | repeat-01 collected 26/26 workers (455 items) tests 175 done 0 failed | 26 in flight, oldest 57s gw25 tests/test_output.py::test_provider_timer_thread_survives_live_update_errors
...............................F[contention-failure] call tests/test_output.py::test_provider_timer_thread_survives_live_update_errors: def test_provider_timer_thread_survives_live_update_errors() -> None:
        """A Live.update exception must not kill the named timer thread."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        with (
            patch("sase.output._PROVIDER_TIMER_INTERVAL_SECONDS", 0),
            patch.object(Live, "update", side_effect=RuntimeError("display boom")),
            patch("sase.output.time.sleep", return_value=None),
            provider_timer("Short operation"),
        ):
>           timer_thread = _wait_for_provider_timer_thread(existing_thread_ids)
                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_output.py:125: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {140622251275968, 140622625310592}

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
......... [  5%]
....F[contention-failure] call tests/test_output.py::test_provider_timer_thread_starts_before_live_enter: def test_provider_timer_thread_starts_before_live_enter() -> None:
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

existing_ids = {139670658741952, 139671112337280}

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
..........................[contention-diag] +232s soak 28p/165t rss 9.2G pss 8.5G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.0G pss 8.2G | host avail 34.7G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 21.58 | cgroup 8.7G/max oom_kill 0 | free scratch 302.9G/44891907i tmp 26.1G/985689i workspace 302.9G/44891907i | repeat-01 collected 26/26 workers (455 items) tests 244 done 2 failed | 26 in flight, oldest 49s gw23 tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom
.........F[contention-failure] call tests/test_output.py::test_provider_timer_stops_background_thread: def test_provider_timer_stops_background_thread() -> None:
        """Stops the timer thread when the context exits."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        timer_thread: threading.Thread | None = None
    
        with patch("sase.output.time.sleep", return_value=None):
            with provider_timer("Short operation"):
>               timer_thread = _wait_for_provider_timer_thread(existing_thread_ids)
                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_output.py:109: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {139883770652352, 139884153214848}

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
......[contention-diag] +248s soak 31p/159t rss 9.4G pss 8.7G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.2G pss 8.4G, 3 descendant rss 0.0G pss 0.0G | host avail 29.9G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 15.21 | cgroup 8.9G/max oom_kill 0 | free scratch 302.9G/44891679i tmp 26.1G/985689i workspace 302.9G/44891679i | scratch used 0.6G in 100065 entries (truncated) | repeat-01 collected 26/26 workers (455 items) tests 257 done 3 failed | 26 in flight, oldest 54s gw22 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
...............[contention-diag] +265s soak 28p/188t rss 9.3G pss 8.5G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 9.0G pss 8.3G | host avail 33.9G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 0.0 cpu 23.28 | cgroup 8.8G/max oom_kill 0 | free scratch 302.8G/44891346i tmp 26.1G/985689i workspace 302.8G/44891346i | repeat-01 collected 26/26 workers (455 items) tests 277 done 3 failed | 26 in flight, oldest 71s gw22 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
F......... [  6%]
........[contention-diag] +280s soak 28p/196t rss 9.0G pss 8.2G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.8G pss 8.0G | host avail 33.1G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.0 cpu 23.43 | cgroup 8.5G/max oom_kill 0 | free scratch 302.8G/44891149i tmp 26.1G/985689i workspace 302.8G/44891149i | repeat-01 collected 26/26 workers (455 items) tests 296 done 4 failed | 26 in flight, oldest 69s gw4 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.........[contention-diag] +295s soak 31p/193t rss 9.1G pss 8.3G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.8G pss 8.1G, 3 descendant rss 0.0G pss 0.0G | host avail 32.0G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.01 | cgroup 8.6G/max oom_kill 0 | free scratch 302.8G/44891009i tmp 26.1G/985689i workspace 302.8G/44891009i | repeat-01 collected 26/26 workers (455 items) tests 302 done 4 failed | 26 in flight, oldest 71s gw25 tests/ace/tui/test_statistics_pane_filters.py::test_custom_range_accepts_valid_input_and_rejects_invalid_input
............................[contention-diag] +311s soak 30p/166t rss 9.1G pss 8.3G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.8G pss 8.1G, 2 descendant rss 0.0G pss 0.0G | host avail 32.7G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.47 | cgroup 8.6G/max oom_kill 0 | free scratch 302.3G/44890568i tmp 26.1G/985689i workspace 302.3G/44890568i | repeat-01 collected 26/26 workers (455 items) tests 331 done 4 failed | 26 in flight, oldest 33s gw2 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
................[contention-diag] +326s soak 31p/184t rss 8.9G pss 8.1G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.6G pss 7.8G, 3 descendant rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.01 | cgroup 8.4G/max oom_kill 0 | free scratch 302.3G/44890303i tmp 26.1G/985689i workspace 302.3G/44890303i | repeat-01 collected 26/26 workers (455 items) tests 348 done 4 failed | 26 in flight, oldest 49s gw2 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.......[contention-diag] +341s soak 30p/198t rss 8.9G pss 8.1G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.6G pss 7.8G, 2 descendant rss 0.0G pss 0.0G | host avail 29.3G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 14.71 | cgroup 8.4G/max oom_kill 0 | free scratch 302.3G/44890137i tmp 26.1G/985689i workspace 302.3G/44890137i | repeat-01 collected 26/26 workers (455 items) tests 356 done 4 failed | 26 in flight, oldest 64s gw2 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.... [  7%]
.............[contention-diag] +357s soak 31p/164t rss 8.9G pss 8.1G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.6G pss 7.9G, 3 descendant rss 0.0G pss 0.0G | host avail 28.7G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 11.41 | cgroup 8.4G/max oom_kill 0 | free scratch 302.1G/44889408i tmp 26.1G/985689i workspace 302.1G/44889408i | repeat-01 collected 26/26 workers (455 items) tests 373 done 4 failed | 25 in flight, oldest 80s gw2 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
....[contention-diag] +372s soak 29p/187t rss 8.9G pss 8.1G swap 0.0G majflt 11 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.7G pss 7.9G, 1 descendant rss 0.0G pss 0.0G | host avail 28.0G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 10.53 | cgroup 8.4G/max oom_kill 0 | free scratch 302.1G/44889004i tmp 26.1G/985689i workspace 302.1G/44889004i | scratch used 0.4G in 46314 entries (truncated) | repeat-01 collected 26/26 workers (455 items) tests 377 done 4 failed | 26 in flight, oldest 66s gw25 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.......[contention-diag] +390s soak 29p/201t rss 8.4G pss 7.8G swap 0.0G majflt 12 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.2G pss 7.6G, 1 descendant rss 0.0G pss 0.0G | host avail 17.7G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.96/0.78 io 0.22 cpu 9.89 | cgroup 8.0G/max oom_kill 0 | free scratch 302.8G/44899751i tmp 26.1G/985689i workspace 302.8G/44899751i | repeat-01 collected 26/26 workers (455 items) tests 384 done 4 failed | 26 in flight, oldest 82s gw8 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.......................[contention-diag] +405s soak 29p/176t rss 8.5G pss 7.8G swap 0.0G majflt 13 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.2G pss 7.6G, 1 descendant rss 0.0G pss 0.0G | host avail 22.2G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.19/0.15 io 0.21 cpu 9.37 | cgroup 8.0G/max oom_kill 0 | free scratch 302.4G/44893404i tmp 26.1G/985688i workspace 302.4G/44893404i | repeat-01 collected 26/26 workers (455 items) tests 407 done 4 failed | 26 in flight, oldest 85s gw21 tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
.[contention-diag] +420s soak 30p/205t rss 8.5G pss 7.8G swap 0.0G majflt 13 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.2G pss 7.6G, 2 descendant rss 0.0G pss 0.0G | host avail 21.2G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.03 io 0.11 cpu 10.53 | cgroup 8.1G/max oom_kill 0 | free scratch 302.4G/44893044i tmp 26.1G/985688i workspace 302.4G/44893044i | repeat-01 collected 26/26 workers (455 items) tests 408 done 4 failed | 26 in flight, oldest 51s gw22 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
............[contention-diag] +436s soak 28p/202t rss 8.5G pss 7.8G swap 0.0G majflt 35 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.2G pss 7.6G | host avail 24.1G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 11.05 | cgroup 8.1G/max oom_kill 0 | free scratch 302.4G/44892942i tmp 26.1G/985688i workspace 302.4G/44892942i | repeat-01 collected 26/26 workers (455 items) tests 418 done 4 failed | 21 in flight, oldest 44s gw15 tests/ace/tui/test_statistics_pane_filters.py::test_custom_range_accepts_valid_input_and_rejects_invalid_input
............ [  7%]
.........[contention-diag] +451s soak 28p/146t rss 8.5G pss 7.8G swap 0.0G majflt 35 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.2G pss 7.6G | host avail 23.7G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 12.93 | cgroup 8.1G/max oom_kill 0 | free scratch 302.4G/44892946i tmp 26.1G/985688i workspace 302.4G/44892946i | repeat-01 collected 26/26 workers (455 items) tests 438 done 4 failed | 11 in flight, oldest 50s gw20 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
......[contention-diag] +466s soak 28p/149t rss 8.5G pss 7.8G swap 0.0G majflt 35 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.2G pss 7.6G | host avail 25.9G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 16.74 | cgroup 8.1G/max oom_kill 0 | free scratch 302.4G/44892907i tmp 26.1G/985688i workspace 302.4G/44892907i | repeat-01 collected 26/26 workers (455 items) tests 447 done 4 failed | 8 in flight, oldest 51s gw21 tests/ace/tui/test_statistics_pane_filters.py::test_custom_range_accepts_valid_input_and_rejects_invalid_input
.......[contention-diag] +482s soak 28p/122t rss 8.5G pss 7.8G swap 0.0G majflt 35 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 8.3G pss 7.6G | host avail 25.2G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 14.72 | cgroup 8.1G/max oom_kill 0 | free scratch 302.5G/44892947i tmp 26.1G/985685i workspace 302.5G/44892947i | repeat-01 collected 26/26 workers (455 items) tests 452 done 4 failed | 1 in flight, oldest 31s gw16 tests/ace/tui/test_statistics_pane_filters.py::test_project_filter_label_submits_canonical_key_across_reload_paths
.                                                  [  7%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________ test_provider_timer_thread_survives_live_update_errors ____________
[gw25] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_provider_timer_thread_survives_live_update_errors() -> None:
        """A Live.update exception must not kill the named timer thread."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        with (
            patch("sase.output._PROVIDER_TIMER_INTERVAL_SECONDS", 0),
            patch.object(Live, "update", side_effect=RuntimeError("display boom")),
            patch("sase.output.time.sleep", return_value=None),
            provider_timer("Short operation"),
        ):
>           timer_thread = _wait_for_provider_timer_thread(existing_thread_ids)
                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_output.py:125: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {140622251275968, 140622625310592}

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
_____________ test_provider_timer_thread_starts_before_live_enter ______________
[gw2] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

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

existing_ids = {139670658741952, 139671112337280}

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
✅ Short operation completed in 01:03
_________________ test_provider_timer_stops_background_thread __________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_provider_timer_stops_background_thread() -> None:
        """Stops the timer thread when the context exits."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        timer_thread: threading.Thread | None = None
    
        with patch("sase.output.time.sleep", return_value=None):
            with provider_timer("Short operation"):
>               timer_thread = _wait_for_provider_timer_thread(existing_thread_ids)
                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_output.py:109: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {139883770652352, 139884153214848}

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
✅ Short operation completed in 01:00
_________________ test_provider_timer_stops_background_thread __________________
[gw21] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_provider_timer_stops_background_thread() -> None:
        """Stops the timer thread when the context exits."""
        existing_thread_ids = {thread.ident for thread in threading.enumerate()}
        timer_thread: threading.Thread | None = None
    
        with patch("sase.output.time.sleep", return_value=None):
            with provider_timer("Short operation"):
>               timer_thread = _wait_for_provider_timer_thread(existing_thread_ids)
                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_output.py:109: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

existing_ids = {140520928048832, 140521386338176}

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
✅ Short operation completed in 01:06
============================= slowest 20 durations =============================
95.76s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
91.43s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
83.08s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
82.81s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
82.00s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
81.66s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
74.21s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
73.59s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
72.95s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
72.86s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
72.85s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
72.28s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
72.10s call     tests/ace/tui/test_statistics_pane_filters.py::test_custom_range_accepts_valid_input_and_rejects_invalid_input
71.34s call     tests/completion/test_update_refresh_soak.py::test_three_update_cycles_refresh_bash_fish_and_zsh
66.23s call     tests/test_output.py::test_provider_timer_stops_background_thread
63.60s call     tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
63.54s call     tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
63.48s call     tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
63.36s call     tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
63.30s call     tests/test_output.py::test_provider_timer_thread_starts_before_live_enter
=========================== short test summary info ============================
FAILED tests/test_output.py::test_provider_timer_thread_survives_live_update_errors
FAILED tests/test_output.py::test_provider_timer_thread_starts_before_live_enter
FAILED tests/test_output.py::test_provider_timer_stops_background_thread - As...
FAILED tests/test_output.py::test_provider_timer_stops_background_thread - As...
================== 4 failed, 451 passed in 490.07s (0:08:10) ===================
[contention-diag] +497s soak 2p/2t rss 0.3G pss 0.2G swap 0.0G majflt 8 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G | host avail 34.5G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.51 cpu 9.74 | cgroup 0.7G/max oom_kill 0 | free scratch 302.5G/44926986i tmp 26.1G/984221i workspace 302.5G/44926986i | scratch used 0.3G in 36746 entries (truncated) | repeat-01 collected 26/26 workers (455 items) tests 455 done 4 failed | 4 hazardous kill call(s)
[contention-diag] +514s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 1 | 1 parent rss 0.0G pss 0.0G | host avail 36.2G/62.7G swapfree 48.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.28 cpu 1.96 | cgroup 0.8G/max oom_kill 0 | free scratch 303.2G/45057923i tmp 26.1G/984221i workspace 303.2G/45057923i | repeat-01 collected 26/26 workers (455 items) tests 455 done 4 failed | 4 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 514s, 34 samples, 0 signal(s); peaks: cgroup_current 8.9G, min_free_scratch 302.1G, min_free_tmp 26.1G, min_free_workspace 302.1G, min_inodes_scratch 44889004, min_inodes_tmp 984221, min_inodes_workspace 44889004, min_mem_available 17.7G, min_swap_free 47.9G, oom_kill_delta 0, pressure_memory_full 0.78, pswpin_delta 25197, pswpout_delta 17562, scratch_bytes 0.6G, soak_procs 33, soak_pss 8.7G, soak_rss 9.4G, soak_swap 0.0G, soak_threads 205

contention tally: 3 node(s) failed across 1 repeat(s) in 513.8s; red repeats: 1
  1/1  tests/test_output.py::test_provider_timer_stops_background_thread  (repeats 1)
  1/1  tests/test_output.py::test_provider_timer_thread_starts_before_live_enter  (repeats 1)
  1/1  tests/test_output.py::test_provider_timer_thread_survives_live_update_errors  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics
error: recipe `test-contention` failed on line 779 with exit code 1

