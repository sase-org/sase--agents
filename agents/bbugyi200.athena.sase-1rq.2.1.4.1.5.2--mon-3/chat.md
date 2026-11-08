# Chat History - ace-run (sase-1rq.2.1.4.1.5.2--mon-3)

- **TIMESTAMP:** 2026-11-08 11:57:18 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-1rq.2.1.4.1.5.2--mon-3

## Prompt

sase monitor start --command 'env SASE_CONTENTION_REPEAT=1 SASE_CONTENTION_WORKERS=26 PYTHONUNBUFFERED=1 taskset -c 0,1 timeout 90m /tmp/sase-1rq-runtime-py312/bin/python tools/run_pytest contention' --reason 'Full default Python 3.12 contention repeat after nested-pytest, TUI wait, fakey-start, and drain-grandchild hang-guard repairs for sase-1rq.2.1.4.1.5.2'

## Response

sase: running unwrapped (no profile (monitor.tool_wrap is verify))
contention soak: 1 repeat(s), 26 workers, dist=sharded
contention shards: each worker collects and runs its own 215-219 of 5671 test files (.pytest_cache/sase-contention/shards.json)

---------- contention repeat 1/1 ----------
[contention-diag] root pid 1783706, sampler pid 1783849 on cpus 0-63 (soak cpus 0-1), python 3.12.13, 64 cpus, host mem 62.7G swap 64.0G, cgroup /user.slice/user-1000.slice/user@1000.service/app.slice/sase-proc-527930-1794152293329918488.scope max max, out /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-contention/diagnostics
[contention-diag] +0s soak 2p/2t rss 0.1G pss 0.0G swap 0.0G majflt 101 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.0G pss 0.0G | host avail 45.9G/62.7G swapfree 54.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.48 cpu 0.0 | cgroup 0.1G/max oom_kill 0 | free scratch 297.5G/45134305i tmp 29.7G/1015669i workspace 297.5G/45134305i | scratch used 0.0G in 13 entries | progress none yet
============================= test session starts ==============================
platform linux -- Python 3.12.13, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: inline-snapshot-0.32.5, mock-3.15.1, hypothesis-6.151.9, cov-7.0.0, asyncio-1.3.0, xdist-3.8.0
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 26/26 workers
[contention-diag] +15s soak 28p/80t rss 2.1G pss 1.8G swap 0.0G majflt 163 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 2.0G pss 1.7G | host avail 44.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.32 cpu 16.43 | cgroup 1.9G/max oom_kill 0 | free scratch 297.5G/45134197i tmp 29.7G/1015669i workspace 297.5G/45134197i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +30s soak 28p/80t rss 3.4G pss 3.1G swap 1.1G majflt 740 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 3.3G pss 3.0G | host avail 43.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.25 cpu 22.56 | cgroup 3.2G/max oom_kill 0 | free scratch 297.5G/45134210i tmp 29.7G/1015669i workspace 297.5G/45134210i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +46s soak 28p/80t rss 4.6G pss 4.2G swap 1.3G majflt 751 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 4.5G pss 4.1G | host avail 41.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.82 cpu 23.41 | cgroup 4.3G/max oom_kill 0 | free scratch 297.5G/45134134i tmp 29.7G/1015669i workspace 297.5G/45134134i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +61s soak 29p/88t rss 5.3G pss 4.9G swap 1.2G majflt 1089 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 5.2G pss 4.9G, 1 descendant rss 0.0G pss 0.0G | host avail 39.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.51 cpu 20.61 | cgroup 5.1G/max oom_kill 0 | free scratch 297.5G/45134109i tmp 29.7G/1015669i workspace 297.5G/45134109i | repeat-01 collected 0/26 workers (0 items) tests 0 done 0 failed
[contention-diag] +76s soak 28p/89t rss 6.1G pss 5.7G swap 1.2G majflt 1156 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.0G pss 5.6G | host avail 41.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.2 cpu 27.19 | cgroup 6.0G/max oom_kill 0 | free scratch 297.5G/45134047i tmp 29.7G/1015664i workspace 297.5G/45134047i | repeat-01 collected 2/26 workers (4689 items) tests 0 done 0 failed
contention shards: 26 workers collected 60615 items in total (2020-2558 per worker)
26 workers [2465 items]

........................................................................ [  3%]
........................................................................ [  6%]
........................................................................ [  9%]
..................................[contention-diag] +91s soak 29p/94t rss 6.6G pss 6.2G swap 1.2G majflt 1669 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 6.5G pss 6.1G, 1 descendant rss 0.0G pss 0.0G | host avail 40.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 7.04 cpu 33.03 | cgroup 6.6G/max oom_kill 0 | free scratch 297.5G/45132954i tmp 29.7G/1015664i workspace 297.5G/45132954i | repeat-01 collected 26/26 workers (60615 items) tests 216 done 0 failed | 25 in flight, oldest 2s gw20 tests/ace/test_revert_agent_import_order.py::test_module_imports_first_in_a_fresh_interpreter[sase.ace.revert_agent_resolution]
...................................... [ 13%]
........................................................................ [ 16%]
........................................................................ [ 19%]
........................................................................ [ 23%]
........................................................................ [ 26%]
........................................................................ [ 29%]
........................................................................ [ 33%]
........................................................................ [ 36%]
........................................................................ [ 39%]
........................................................................ [ 43%]
........................................................................ [ 46%]
...[contention-diag] +106s soak 31p/137t rss 7.2G pss 6.7G swap 1.1G majflt 2151 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.0G pss 6.5G, 3 descendant rss 0.1G pss 0.1G | host avail 40.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.87 cpu 37.24 | cgroup 7.0G/max oom_kill 0 | free scratch 297.5G/45130993i tmp 29.7G/1015659i workspace 297.5G/45130993i | repeat-01 collected 26/26 workers (60615 items) tests 999 done 0 failed | 26 in flight, oldest 17s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
..................................................................... [ 49%]
........................................................................ [ 53%]
........................................................................ [ 56%]
........................................[contention-diag] +122s soak 29p/151t rss 7.5G pss 6.9G swap 1.1G majflt 2211 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.3G pss 6.8G, 1 descendant rss 0.1G pss 0.0G | host avail 39.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.41 cpu 36.57 | cgroup 7.3G/max oom_kill 0 | free scratch 297.5G/45130383i tmp 29.7G/1015660i workspace 297.5G/45130383i | scratch used 0.0G in 3457 entries | repeat-01 collected 26/26 workers (60615 items) tests 1263 done 0 failed | 26 in flight, oldest 32s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
................................ [ 59%]
........................................................................ [ 63%]
........................................................................ [ 66%]
........................................................................ [ 69%]
........................................................................ [ 73%]
..........[contention-diag] +137s soak 30p/164t rss 7.7G pss 7.2G swap 1.0G majflt 2285 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.5G pss 7.0G, 2 descendant rss 0.1G pss 0.1G | host avail 40.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.53 cpu 34.96 | cgroup 7.5G/max oom_kill 0 | free scratch 297.5G/45129566i tmp 29.7G/1015660i workspace 297.5G/45129566i | repeat-01 collected 26/26 workers (60615 items) tests 1592 done 0 failed | 26 in flight, oldest 47s gw12 tests/ace/tui/command_line/test_transcript_blocks_keys.py::test_block_keys_select_move_and_switch_hints
.............................................................. [ 76%]
........................................................................ [ 79%]
........................................................................ [ 83%]
........................................[contention-diag] +152s soak 34p/174t rss 7.9G pss 7.3G swap 1.0G majflt 2367 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.6G pss 7.1G, 6 descendant rss 0.1G pss 0.1G | host avail 38.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 31.91 | cgroup 7.7G/max oom_kill 0 | free scratch 297.5G/45128856i tmp 29.7G/1015655i workspace 297.5G/45128856i | repeat-01 collected 26/26 workers (60615 items) tests 1838 done 0 failed | 26 in flight, oldest 59s gw21 tests/ace/tui/actions/test_agent_archive_shelf.py::test_typing_in_the_filter_bar_never_counts_until_commit
................................ [ 86%]
........................................................................ [ 89%]
.....................................................[contention-diag] +167s soak 33p/183t rss 8.0G pss 7.4G swap 1.0G majflt 2381 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 7.8G pss 7.3G, 5 descendant rss 0.1G pss 0.0G | host avail 35.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 28.24 | cgroup 7.8G/max oom_kill 0 | free scratch 297.5G/45128420i tmp 29.7G/1015655i workspace 297.5G/45128420i | repeat-01 collected 26/26 workers (60615 items) tests 1974 done 0 failed | 26 in flight, oldest 55s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................... [ 93%]
........................................................................ [ 96%]
........................................................................ [ 99%]
.......................................................[contention-diag] +182s soak 35p/227t rss 8.3G pss 7.7G swap 1.1G majflt 2381 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.0G pss 7.4G, 7 descendant rss 0.2G pss 0.1G | host avail 35.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 27.8 | cgroup 8.1G/max oom_kill 0 | free scratch 297.4G/45126073i tmp 29.7G/1015655i workspace 297.4G/45126073i | repeat-01 collected 26/26 workers (60615 items) tests 2195 done 0 failed | 26 in flight, oldest 70s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................. [103%]
........................................................................ [106%]
........................................................................ [109%]
.............................................................[contention-diag] +198s soak 37p/224t rss 8.5G pss 7.8G swap 1.0G majflt 2427 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.1G pss 7.6G, 9 descendant rss 0.2G pss 0.1G | host avail 34.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 22.64 | cgroup 8.2G/max oom_kill 0 | free scratch 297.4G/45126847i tmp 29.7G/1015655i workspace 297.4G/45126847i | repeat-01 collected 26/26 workers (60615 items) tests 2429 done 0 failed | 26 in flight, oldest 85s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........... [113%]
........................................................................ [116%]
................................................[contention-diag] +213s soak 36p/215t rss 8.7G pss 8.1G swap 1.1G majflt 2433 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.3G pss 7.7G, 8 descendant rss 0.3G pss 0.2G | host avail 32.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.81 | cgroup 8.4G/max oom_kill 0 | free scratch 297.4G/45126486i tmp 29.7G/1015655i workspace 297.4G/45126486i | repeat-01 collected 26/26 workers (60615 items) tests 2567 done 0 failed | 26 in flight, oldest 100s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................ [119%]
........................................................................ [123%]
........................................................................ [126%]
...........[contention-diag] +228s soak 36p/221t rss 8.7G pss 8.1G swap 1.0G majflt 2486 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.8G, 8 descendant rss 0.2G pss 0.1G | host avail 32.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 0.0 cpu 24.99 | cgroup 8.5G/max oom_kill 0 | free scratch 297.4G/45125953i tmp 29.7G/1015653i workspace 297.4G/45125953i | repeat-01 collected 26/26 workers (60615 items) tests 2742 done 0 failed | 26 in flight, oldest 116s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................................. [129%]
........................................................................ [133%]
........[contention-diag] +243s soak 36p/223t rss 8.9G pss 8.2G swap 1.1G majflt 2513 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.4G pss 7.9G, 8 descendant rss 0.3G pss 0.2G | host avail 31.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.0 cpu 24.18 | cgroup 8.6G/max oom_kill 0 | free scratch 297.3G/45125550i tmp 29.7G/1015655i workspace 297.3G/45125550i | scratch used 0.1G in 7887 entries | repeat-01 collected 26/26 workers (60615 items) tests 2878 done 0 failed | 26 in flight, oldest 131s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................................ [136%]
........................................................................ [139%]
........................................................................ [143%]
....................[contention-diag] +259s soak 36p/218t rss 9.1G pss 8.4G swap 1.1G majflt 2592 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.6G pss 8.0G, 8 descendant rss 0.3G pss 0.2G | host avail 35.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.11 | cgroup 8.8G/max oom_kill 0 | free scratch 297.4G/45124879i tmp 29.7G/1015655i workspace 297.4G/45124879i | repeat-01 collected 26/26 workers (60615 items) tests 3102 done 0 failed | 26 in flight, oldest 146s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.................................................... [146%]
.............................................[contention-diag] +274s soak 33p/233t rss 8.9G pss 8.2G swap 1.0G majflt 2611 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.1G, 5 descendant rss 0.1G pss 0.0G | host avail 35.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.91 | cgroup 8.7G/max oom_kill 0 | free scratch 297.4G/45124534i tmp 29.7G/1015655i workspace 297.4G/45124534i | repeat-01 collected 26/26 workers (60615 items) tests 3213 done 0 failed | 26 in flight, oldest 161s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................F[contention-failure] call tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding: fut = <coroutine object AcePage.press at 0x7fbf1f14d560>, timeout = 5.0

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

../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/asyncio/tasks.py:520: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:366: in press
    await self._pilot.press(*keys)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/pilot.py:83: in press
    await self._app._press_keys(keys)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/app.py:1994: in _press_keys
    await wait_for_idle(0)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/_wait.py:29: in wait_for_idle
    await sleep(SLEEP_GRANULARITY)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

delay = 0.02, result = None

    async def sleep(delay, result=None):
        """Coroutine that completes after a given time (in seconds)."""
        if delay <= 0:
            await __sleep0()
            return result
    
        loop = events.get_running_loop()
        future = loop.create_future()
        h = loop.call_later(delay,
                            futures._set_result_unless_cancelled,
                            future, result)
        try:
>           return await future
                   ^^^^^^^^^^^^
E           asyncio.exceptions.CancelledError

../../../../../../share/uv/p
...... [149%]
.[contention-diag] +289s soak 35p/234t rss 9.0G pss 8.3G swap 1.0G majflt 2611 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.7G pss 8.2G, 7 descendant rss 0.1G pss 0.0G | host avail 35.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.43 | cgroup 8.8G/max oom_kill 0 | free scratch 297.4G/45124392i tmp 29.7G/1015655i workspace 297.4G/45124392i | repeat-01 collected 26/26 workers (60615 items) tests 3233 done 0 failed | 26 in flight, oldest 177s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..............................[contention-diag] +304s soak 35p/250t rss 9.2G pss 8.5G swap 1.0G majflt 2611 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.8G pss 8.2G, 7 descendant rss 0.2G pss 0.1G | host avail 37.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 26.36 | cgroup 8.9G/max oom_kill 0 | free scratch 297.4G/45124144i tmp 29.7G/1015655i workspace 297.4G/45124144i | repeat-01 collected 26/26 workers (60615 items) tests 3269 done 1 failed | 26 in flight, oldest 192s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................................... [152%]
....................................................................[contention-diag] +320s soak 34p/230t rss 9.2G pss 8.5G swap 1.0G majflt 2615 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 8.9G pss 8.3G, 6 descendant rss 0.1G pss 0.1G | host avail 35.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 33.6 | cgroup 9.0G/max oom_kill 0 | free scratch 297.4G/45123736i tmp 29.7G/1015655i workspace 297.4G/45123736i | repeat-01 collected 26/26 workers (60615 items) tests 3375 done 1 failed | 26 in flight, oldest 207s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.... [156%]
........................................................................ [159%]
........................................................................ [162%]
.......................[contention-diag] +335s soak 33p/227t rss 9.2G pss 8.5G swap 1.0G majflt 2623 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.0G pss 8.4G, 5 descendant rss 0.1G pss 0.0G | host avail 34.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.05 | cgroup 9.0G/max oom_kill 0 | free scratch 297.4G/45123263i tmp 29.7G/1015655i workspace 297.4G/45123263i | repeat-01 collected 26/26 workers (60615 items) tests 3545 done 1 failed | 26 in flight, oldest 222s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
................................................. [166%]
...............................[contention-diag] +350s soak 35p/263t rss 9.3G pss 8.7G swap 1.0G majflt 2624 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 7 descendant rss 0.1G pss 0.0G | host avail 34.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.94 | cgroup 9.1G/max oom_kill 0 | free scratch 297.4G/45122902i tmp 29.7G/1015655i workspace 297.4G/45122902i | repeat-01 collected 26/26 workers (60615 items) tests 3630 done 1 failed | 26 in flight, oldest 238s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
......................................... [169%]
........................................................................ [172%]
.......[contention-diag] +365s soak 34p/260t rss 9.4G pss 8.7G swap 1.0G majflt 2625 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.1G pss 8.5G, 6 descendant rss 0.1G pss 0.1G | host avail 33.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.36 | cgroup 9.2G/max oom_kill 0 | free scratch 297.4G/45122556i tmp 29.7G/1015655i workspace 297.4G/45122556i | scratch used 0.1G in 10800 entries | repeat-01 collected 26/26 workers (60615 items) tests 3744 done 1 failed | 26 in flight, oldest 253s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................[contention-diag] +381s soak 40p/271t rss 9.6G pss 8.9G swap 1.0G majflt 2625 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.2G pss 8.6G, 12 descendant rss 0.2G pss 0.1G | host avail 32.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 38.41 | cgroup 9.3G/max oom_kill 0 | free scratch 297.4G/45122364i tmp 29.7G/1015655i workspace 297.4G/45122364i | repeat-01 collected 26/26 workers (60615 items) tests 3768 done 1 failed | 26 in flight, oldest 268s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
.......................................... [176%]
........................................................................ [179%]
..[contention-diag] +396s soak 38p/252t rss 9.5G pss 8.8G swap 1.0G majflt 2625 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 10 descendant rss 0.1G pss 0.0G | host avail 31.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.72 | cgroup 9.3G/max oom_kill 0 | free scratch 297.2G/45122019i tmp 29.7G/1015655i workspace 297.2G/45122019i | repeat-01 collected 26/26 workers (60615 items) tests 3882 done 1 failed | 24 in flight, oldest 283s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................................... [182%]
................[contention-diag] +411s soak 41p/290t rss 9.6G pss 8.9G swap 1.0G majflt 2625 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 13 descendant rss 0.2G pss 0.1G | host avail 37.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.37 | cgroup 9.4G/max oom_kill 0 | free scratch 297.4G/45121744i tmp 29.7G/1015655i workspace 297.4G/45121744i | repeat-01 collected 26/26 workers (60615 items) tests 3975 done 1 failed | 26 in flight, oldest 299s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........................................................ [186%]
.................................................[contention-diag] +426s soak 40p/254t rss 9.7G pss 9.0G swap 1.0G majflt 2625 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.3G pss 8.7G, 12 descendant rss 0.2G pss 0.1G | host avail 37.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.36 | cgroup 9.4G/max oom_kill 0 | free scratch 297.4G/45121412i tmp 29.7G/1015655i workspace 297.4G/45121412i | repeat-01 collected 26/26 workers (60615 items) tests 4078 done 1 failed | 26 in flight, oldest 314s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................... [189%]
........................................................................ [192%]
............................[contention-diag] +442s soak 37p/246t rss 9.8G pss 9.1G swap 1.0G majflt 2639 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 9 descendant rss 0.3G pss 0.2G | host avail 36.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.66 | cgroup 9.6G/max oom_kill 0 | free scratch 297.4G/45121063i tmp 29.7G/1015655i workspace 297.4G/45121063i | repeat-01 collected 26/26 workers (60615 items) tests 4187 done 1 failed | 26 in flight, oldest 329s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
............................................ [196%]
..................[contention-diag] +457s soak 36p/280t rss 9.8G pss 9.1G swap 1.0G majflt 2678 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.4G pss 8.8G, 8 descendant rss 0.2G pss 0.1G | host avail 37.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.48 | cgroup 9.6G/max oom_kill 0 | free scratch 297.4G/45120817i tmp 29.7G/1015655i workspace 297.4G/45120817i | repeat-01 collected 26/26 workers (60615 items) tests 4264 done 1 failed | 26 in flight, oldest 345s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
...................................................... [199%]
.................[contention-diag] +472s soak 30p/244t rss 9.8G pss 9.2G swap 1.0G majflt 2702 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.5G pss 8.9G, 2 descendant rss 0.2G pss 0.1G | host avail 35.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 23.25 | cgroup 9.7G/max oom_kill 0 | free scratch 297.4G/45120527i tmp 29.7G/1015655i workspace 297.4G/45120527i | repeat-01 collected 26/26 workers (60615 items) tests 4336 done 1 failed | 26 in flight, oldest 360s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
....................................................... [202%]
...........................................[contention-diag] +488s soak 30p/250t rss 9.8G pss 9.1G swap 1.0G majflt 2702 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 8.9G, 2 descendant rss 0.1G pss 0.0G | host avail 34.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.73 | cgroup 9.6G/max oom_kill 0 | free scratch 297.4G/45120129i tmp 29.7G/1015655i workspace 297.4G/45120129i | scratch used 0.1G in 13167 entries | repeat-01 collected 26/26 workers (60615 items) tests 4433 done 1 failed | 26 in flight, oldest 375s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
..................[contention-diag] +503s soak 28p/263t rss 9.8G pss 9.1G swap 1.0G majflt 2703 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G | host avail 32.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.58 | cgroup 9.6G/max oom_kill 0 | free scratch 297.4G/45119727i tmp 29.7G/1015655i workspace 297.4G/45119727i | repeat-01 collected 26/26 workers (60615 items) tests 4453 done 1 failed | 26 in flight, oldest 391s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
........... [206%]
.........................[contention-diag] +518s soak 29p/248t rss 9.8G pss 9.2G swap 1.0G majflt 2724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.6G pss 9.0G, 1 descendant rss 0.0G pss 0.0G | host avail 31.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.8 | cgroup 9.7G/max oom_kill 0 | free scratch 297.4G/45119070i tmp 29.7G/1015655i workspace 297.4G/45119070i | repeat-01 collected 26/26 workers (60615 items) tests 4488 done 1 failed | 26 in flight, oldest 61s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
...................[contention-diag] +534s soak 30p/256t rss 9.9G pss 9.3G swap 1.0G majflt 2726 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 2 descendant rss 0.0G pss 0.0G | host avail 29.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.14/0.14 io 0.04 cpu 19.16 | cgroup 9.8G/max oom_kill 0 | free scratch 297.3G/45119172i tmp 29.7G/1015655i workspace 297.3G/45119172i | repeat-01 collected 26/26 workers (60615 items) tests 4506 done 1 failed | 26 in flight, oldest 76s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
............................ [209%]
..................[contention-diag] +549s soak 30p/233t rss 10.0G pss 9.3G swap 1.0G majflt 2724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G, 2 descendant rss 0.1G pss 0.1G | host avail 34.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.11/0.03 io 0.0 cpu 17.91 | cgroup 9.9G/max oom_kill 0 | free scratch 296.9G/45118879i tmp 29.7G/1015655i workspace 296.9G/45118879i | repeat-01 collected 26/26 workers (60615 items) tests 4551 done 1 failed | 26 in flight, oldest 92s gw14 tests/ace/tui/test_artifacts_relation_collapse_interactions.py::test_dot_collapses_and_expands_on_each_relations_pane
...................................................... [212%]
.....................................[contention-diag] +564s soak 28p/228t rss 9.9G pss 9.3G swap 1.0G majflt 2724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.7G pss 9.1G | host avail 35.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.05 cpu 21.07 | cgroup 9.8G/max oom_kill 0 | free scratch 297.8G/45124306i tmp 29.7G/1015654i workspace 297.8G/45124306i | repeat-01 collected 26/26 workers (60615 items) tests 4643 done 1 failed | 26 in flight, oldest 81s gw12 tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough
................................... [216%]
...[contention-diag] +580s soak 28p/244t rss 9.9G pss 9.3G swap 1.0G majflt 2724 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G | host avail 33.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 21.96 | cgroup 9.8G/max oom_kill 0 | free scratch 297.6G/45124005i tmp 29.7G/1015654i workspace 297.6G/45124005i | repeat-01 collected 26/26 workers (60615 items) tests 4682 done 1 failed | 26 in flight, oldest 56s gw25 tests/ace/tui/test_link_follow_entry_points.py::test_matrix_links_panel_key_path_follows_first_chip
.............................................[contention-diag] +595s soak 29p/250t rss 10.0G pss 9.4G swap 1.0G majflt 2725 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 1 descendant rss 0.1G pss 0.1G | host avail 35.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.15 cpu 24.91 | cgroup 9.9G/max oom_kill 0 | free scratch 297.3G/45120480i tmp 29.7G/1015654i workspace 297.3G/45120480i | repeat-01 collected 26/26 workers (60615 items) tests 4727 done 1 failed | 26 in flight, oldest 51s gw19 tests/ace/tui/test_agent_grouping_picker.py::test_agents_default_oo_toggles_panel_layout_once_and_preserves_mode
........................ [219%]
..........[contention-diag] +610s soak 30p/239t rss 10.1G pss 9.4G swap 1.0G majflt 2725 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.8G pss 9.2G, 2 descendant rss 0.1G pss 0.1G | host avail 34.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 24.86 | cgroup 10.0G/max oom_kill 0 | free scratch 297.3G/45120283i tmp 29.7G/1015653i workspace 297.3G/45120283i | scratch used 0.1G in 14938 entries | repeat-01 collected 26/26 workers (60615 items) tests 4758 done 1 failed | 26 in flight, oldest 50s gw13 tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_K_warns_when_finished_and_confirms_when_running
..........................[contention-diag] +626s soak 28p/255t rss 10.0G pss 9.4G swap 1.0G majflt 2725 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G | host avail 34.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.16/0.16 io 0.12 cpu 30.12 | cgroup 10.0G/max oom_kill 0 | free scratch 297.3G/45120090i tmp 29.7G/1015654i workspace 297.3G/45120090i | repeat-01 collected 26/26 workers (60615 items) tests 4787 done 1 failed | 26 in flight, oldest 62s gw10 tests/ace/tui/test_agents_mode_affordances.py::test_zoom_chip_click_restores_zoom
.................................... [222%]
...............................[contention-diag] +641s soak 28p/232t rss 10.1G pss 9.5G swap 1.0G majflt 2725 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G | host avail 32.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 0.02 cpu 24.26 | cgroup 10.0G/max oom_kill 0 | free scratch 297.3G/45119817i tmp 29.7G/1015654i workspace 297.3G/45119817i | repeat-01 collected 26/26 workers (60615 items) tests 4855 done 1 failed | 26 in flight, oldest 56s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
...........[contention-diag] +656s soak 29p/243t rss 10.2G pss 9.5G swap 1.0G majflt 2732 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 9.9G pss 9.3G, 1 descendant rss 0.1G pss 0.1G | host avail 29.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 25.42 | cgroup 10.1G/max oom_kill 0 | free scratch 297.3G/45119673i tmp 29.7G/1015654i workspace 297.3G/45119673i | repeat-01 collected 26/26 workers (60615 items) tests 4864 done 1 failed | 26 in flight, oldest 71s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_other_hint_line
...............[contention-diag] +672s soak 29p/242t rss 10.2G pss 9.6G swap 1.0G majflt 2732 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 1 descendant rss 0.1G pss 0.1G | host avail 29.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 24.86 | cgroup 10.2G/max oom_kill 0 | free scratch 297.1G/45118942i tmp 29.7G/1015654i workspace 297.1G/45118941i | repeat-01 collected 26/26 workers (60615 items) tests 4880 done 1 failed | 26 in flight, oldest 62s gw20 tests/ace/tui/test_agent_archive_remaining_proof.py::test_mounted_deck_splits_survive_archive_round_trip
............... [226%]
..............[contention-diag] +687s soak 29p/228t rss 10.2G pss 9.6G swap 1.0G majflt 2734 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 35.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 37.96 | cgroup 10.1G/max oom_kill 0 | free scratch 297.3G/45119232i tmp 29.7G/1015654i workspace 297.3G/45119232i | repeat-01 collected 26/26 workers (60615 items) tests 4907 done 1 failed | 26 in flight, oldest 56s gw21 tests/ace/tui/test_commits_pane_filters.py::test_commits_filter_bar_rejects_invalid_submit
............[contention-diag] +702s soak 29p/245t rss 10.2G pss 9.6G swap 1.0G majflt 2734 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.0G pss 9.4G, 1 descendant rss 0.0G pss 0.0G | host avail 34.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 35.47 | cgroup 10.2G/max oom_kill 0 | free scratch 297.7G/45119102i tmp 29.7G/1015654i workspace 297.7G/45119102i | repeat-01 collected 26/26 workers (60615 items) tests 4922 done 1 failed | 26 in flight, oldest 62s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_hash_slot_saves_a_query_under_the_agents_live_namespace
.............................................. [229%]
......................................................[contention-diag] +718s soak 34p/243t rss 10.4G pss 9.7G swap 1.0G majflt 2734 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.4G, 6 descendant rss 0.2G pss 0.1G | host avail 32.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 30.14 | cgroup 10.4G/max oom_kill 0 | free scratch 297.7G/45118735i tmp 29.7G/1015654i workspace 297.7G/45118735i | repeat-01 collected 26/26 workers (60615 items) tests 5020 done 1 failed | 26 in flight, oldest 55s gw18 tests/ace/tui/command_line/test_policy_io.py::test_scrolled_out_running_block_is_not_tailed
.................. [232%]
........................................................................ [236%]
......................................................................[contention-diag] +733s soak 28p/211t rss 10.3G pss 9.6G swap 1.0G majflt 2734 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G | host avail 32.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 31.18 | cgroup 10.3G/max oom_kill 0 | free scratch 297.7G/45116686i tmp 29.7G/1015654i workspace 297.7G/45116686i | scratch used 0.1G in 16940 entries | repeat-01 collected 26/26 workers (60615 items) tests 5166 done 1 failed | 26 in flight, oldest 50s gw15 tests/ace/tui/test_node_finder_e2e.py::test_quotation_mark_opens_modal_and_hint_jumps_to_hidden_member
.. [239%]
........................................................................ [242%]
........................................................................ [246%]
........................................................................ [249%]
......[contention-diag] +748s soak 28p/244t rss 10.3G pss 9.7G swap 1.0G majflt 2735 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.1G pss 9.5G | host avail 31.1G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 27.75 | cgroup 10.2G/max oom_kill 0 | free scratch 297.6G/45116066i tmp 29.7G/1015654i workspace 297.6G/45116066i | repeat-01 collected 26/26 workers (60615 items) tests 5399 done 1 failed | 26 in flight, oldest 50s gw1 tests/ace/tui/test_plugins_browser_pane_update.py::test_plugins_pane_update_unknown_toasts
.................................................................. [252%]
.................[contention-diag] +764s soak 28p/270t rss 10.3G pss 9.7G swap 1.0G majflt 2742 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.5G | host avail 34.4G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 24.54 | cgroup 10.3G/max oom_kill 0 | free scratch 297.3G/45115646i tmp 29.7G/1015654i workspace 297.3G/45115646i | repeat-01 collected 26/26 workers (60615 items) tests 5483 done 1 failed | 26 in flight, oldest 59s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
....................................................... [256%]
...........................................[contention-diag] +779s soak 31p/251t rss 10.5G pss 9.8G swap 1.0G majflt 2745 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 3 descendant rss 0.2G pss 0.1G | host avail 33.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.18 cpu 27.69 | cgroup 10.5G/max oom_kill 0 | free scratch 296.5G/45115312i tmp 29.7G/1015654i workspace 296.5G/45115312i | repeat-01 collected 26/26 workers (60615 items) tests 5583 done 1 failed | 26 in flight, oldest 75s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
............................. [259%]
.............[contention-diag] +794s soak 30p/250t rss 10.5G pss 9.8G swap 1.0G majflt 2756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.2G pss 9.6G, 2 descendant rss 0.1G pss 0.0G | host avail 32.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.44 cpu 20.41 | cgroup 10.4G/max oom_kill 0 | free scratch 296.4G/45115032i tmp 29.7G/1015654i workspace 296.4G/45115032i | repeat-01 collected 26/26 workers (60615 items) tests 5628 done 1 failed | 26 in flight, oldest 90s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
................................[contention-diag] +810s soak 29p/285t rss 10.5G pss 9.8G swap 1.0G majflt 2756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.6G, 1 descendant rss 0.0G pss 0.0G | host avail 33.3G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.54/0.36 io 6.7 cpu 17.93 | cgroup 10.5G/max oom_kill 0 | free scratch 296.3G/45114758i tmp 29.7G/1015654i workspace 296.3G/45114758i | repeat-01 collected 26/26 workers (60615 items) tests 5661 done 1 failed | 26 in flight, oldest 105s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
....................[contention-diag] +825s soak 30p/267t rss 10.6G pss 9.9G swap 1.0G majflt 2756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.3G pss 9.7G, 2 descendant rss 0.1G pss 0.1G | host avail 33.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.1/0.07 io 2.45 cpu 21.2 | cgroup 10.6G/max oom_kill 0 | free scratch 304.9G/45123392i tmp 29.7G/1015654i workspace 304.9G/45123392i | repeat-01 collected 26/26 workers (60615 items) tests 5680 done 1 failed | 26 in flight, oldest 121s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
....... [262%]
........................................................................ [266%]
.................[contention-diag] +840s soak 30p/252t rss 10.7G pss 10.0G swap 1.0G majflt 2756 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G, 2 descendant rss 0.1G pss 0.1G | host avail 32.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.38/0.37 io 0.72 cpu 22.14 | cgroup 10.6G/max oom_kill 0 | free scratch 304.9G/45123059i tmp 29.7G/1015654i workspace 304.9G/45123059i | repeat-01 collected 26/26 workers (60615 items) tests 5767 done 1 failed | 26 in flight, oldest 136s gw5 tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
....................................................... [269%]
........................................................................ [272%]
.[contention-diag] +855s soak 30p/232t rss 10.6G pss 9.9G swap 1.0G majflt 2759 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.7G, 2 descendant rss 0.0G pss 0.0G | host avail 32.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 0.14 cpu 25.0 | cgroup 10.5G/max oom_kill 0 | free scratch 304.9G/45122027i tmp 29.7G/1015654i workspace 304.9G/45122027i | scratch used 0.1G in 19695 entries | repeat-01 collected 26/26 workers (60615 items) tests 5889 done 1 failed | 26 in flight, oldest 51s gw9 tests/ace/tui/test_app_title.py::test_on_mount_keeps_initial_title_when_resolver_returns_none
....................................................................... [276%]
........................................................................ [279%]
........................................................[contention-diag] +871s soak 30p/226t rss 10.6G pss 9.9G swap 1.0G majflt 2761 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.8G, 2 descendant rss 0.0G pss 0.0G | host avail 33.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.05/0.05 io 0.07 cpu 27.26 | cgroup 10.5G/max oom_kill 0 | free scratch 304.7G/45121349i tmp 29.7G/1015654i workspace 304.7G/45121349i | repeat-01 collected 26/26 workers (60615 items) tests 6101 done 1 failed | 26 in flight, oldest 66s gw9 tests/ace/tui/test_app_title.py::test_on_mount_keeps_initial_title_when_resolver_returns_none
................ [282%]
........................................................................ [286%]
.........................................[contention-diag] +886s soak 31p/260t rss 10.7G pss 10.0G swap 0.9G majflt 2763 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.4G pss 9.8G, 3 descendant rss 0.1G pss 0.1G | host avail 32.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.01 cpu 25.62 | cgroup 10.6G/max oom_kill 0 | free scratch 304.9G/45120841i tmp 29.7G/1015654i workspace 304.9G/45120841i | repeat-01 collected 26/26 workers (60615 items) tests 6227 done 1 failed | 26 in flight, oldest 70s gw17 tests/ace/tui/modals/test_agent_grouping_modal.py::test_agent_grouping_modal_layout_navigation_enter_and_click
............................... [289%]
........................................................................ [292%]
............................................[contention-diag] +901s soak 29p/234t rss 10.7G pss 10.0G swap 1.0G majflt 2769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G, 1 descendant rss 0.1G pss 0.0G | host avail 33.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.32/0.32 io 0.2 cpu 20.65 | cgroup 10.4G/max oom_kill 0 | free scratch 304.9G/45119774i tmp 29.7G/1015654i workspace 304.9G/45119774i | repeat-01 collected 26/26 workers (60615 items) tests 6378 done 1 failed | 26 in flight, oldest 58s gw7 tests/ace/tui/command_line/test_keymap_config.py::test_menu_moves_with_fixed_arrows_when_history_rebound
............................ [295%]
.....[contention-diag] +917s soak 28p/235t rss 10.7G pss 10.0G swap 1.0G majflt 2769 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.8G | host avail 33.6G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.03 cpu 26.0 | cgroup 10.4G/max oom_kill 0 | free scratch 304.9G/45118639i tmp 29.7G/1015654i workspace 304.9G/45118639i | repeat-01 collected 26/26 workers (60615 items) tests 6410 done 1 failed | 25 in flight, oldest 66s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_keeps_focus_and_jk_navigation
................................................................... [299%]
........................................................................ [302%]
.........................................[contention-diag] +932s soak 30p/241t rss 10.7G pss 10.1G swap 1.0G majflt 2819 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.5G pss 9.9G, 2 descendant rss 0.0G pss 0.0G | host avail 34.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.37/0.37 io 0.0 cpu 29.34 | cgroup 10.4G/max oom_kill 0 | free scratch 304.9G/45118151i tmp 29.7G/1015652i workspace 304.9G/45118151i | repeat-01 collected 26/26 workers (60615 items) tests 6575 done 1 failed | 26 in flight, oldest 60s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_p_during_committed_search_exits_and_opens_picker
............................... [305%]
.......................................[contention-diag] +947s soak 29p/230t rss 10.7G pss 10.1G swap 1.0G majflt 2824 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 35.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.07/0.07 io 0.0 cpu 39.79 | cgroup 10.5G/max oom_kill 0 | free scratch 304.9G/45117831i tmp 29.7G/1015654i workspace 304.9G/45117831i | repeat-01 collected 26/26 workers (60615 items) tests 6663 done 1 failed | 26 in flight, oldest 51s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
................................. [309%]
.......................................[contention-diag] +962s soak 29p/231t rss 10.8G pss 10.1G swap 1.0G majflt 2826 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 33.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.32 cpu 36.97 | cgroup 10.5G/max oom_kill 0 | free scratch 304.9G/45117434i tmp 29.7G/1015654i workspace 304.9G/45117434i | repeat-01 collected 26/26 workers (60615 items) tests 6735 done 1 failed | 26 in flight, oldest 66s gw13 tests/ace/tui/test_artifacts_files_filtering.py::test_filter_bar_kind_cycle_selection_and_empty_copy
...........................[contention-diag] +978s soak 29p/252t rss 10.8G pss 10.2G swap 1.0G majflt 2826 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.6G pss 10.0G, 1 descendant rss 0.0G pss 0.0G | host avail 33.8G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 37.63 | cgroup 10.6G/max oom_kill 0 | free scratch 304.9G/45117318i tmp 29.7G/1015654i workspace 304.9G/45117318i | scratch used 0.1G in 22539 entries | repeat-01 collected 26/26 workers (60615 items) tests 6761 done 1 failed | 26 in flight, oldest 56s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_rail_preserves_row_positions_and_scroll
...... [312%]
........................................................................ [315%]
.......................[contention-diag] +993s soak 29p/211t rss 10.9G pss 10.2G swap 1.0G majflt 2826 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 1 descendant rss 0.1G pss 0.0G | host avail 34.7G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.56 cpu 40.76 | cgroup 10.6G/max oom_kill 0 | free scratch 304.9G/45116939i tmp 29.7G/1015654i workspace 304.9G/45116939i | repeat-01 collected 26/26 workers (60615 items) tests 6857 done 1 failed | 26 in flight, oldest 44s gw24 tests/ace/tui/test_config_center_resume.py::test_write_failure_is_nonfatal_and_same_tab_can_retry
................................................. [319%]
........................................................................ [322%]
.................................[contention-diag] +1008s soak 28p/206t rss 10.9G pss 10.2G swap 1.0G majflt 2826 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G | host avail 33.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 35.36 | cgroup 10.6G/max oom_kill 0 | free scratch 304.9G/45116555i tmp 29.7G/1015654i workspace 304.9G/45116555i | repeat-01 collected 26/26 workers (60615 items) tests 7011 done 1 failed | 26 in flight, oldest 43s gw3 tests/ace/tui/test_artifacts_limit_keys.py::test_beads_limit_all_then_ctrl_k_introduces_page_size
....................................... [325%]
...........................[contention-diag] +1024s soak 30p/242t rss 10.9G pss 10.2G swap 1.0G majflt 2826 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.0G, 2 descendant rss 0.1G pss 0.0G | host avail 34.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 38.83 | cgroup 10.7G/max oom_kill 0 | free scratch 304.9G/45116231i tmp 29.7G/1015654i workspace 304.9G/45116231i | repeat-01 collected 26/26 workers (60615 items) tests 7083 done 1 failed | 26 in flight, oldest 43s gw5 tests/ace/tui/test_artifacts_plans_filtering.py::test_committing_plan_query_updates_idle_bar
............................................. [329%]
...................................................................[contention-diag] +1039s soak 29p/224t rss 10.9G pss 10.3G swap 1.0G majflt 2826 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.7G pss 10.1G, 1 descendant rss 0.0G pss 0.0G | host avail 35.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 45.85 | cgroup 10.7G/max oom_kill 0 | free scratch 304.9G/45115881i tmp 29.7G/1015654i workspace 304.9G/45115881i | repeat-01 collected 26/26 workers (60615 items) tests 7191 done 1 failed | 25 in flight, oldest 55s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
..... [332%]
........................................................................ [335%]
.........................................................[contention-diag] +1054s soak 29p/240t rss 11.0G pss 10.3G swap 1.0G majflt 2826 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.7G pss 10.1G, 1 descendant rss 0.1G pss 0.0G | host avail 34.2G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 49.22 | cgroup 10.7G/max oom_kill 0 | free scratch 304.7G/45115458i tmp 29.7G/1015654i workspace 304.7G/45115458i | repeat-01 collected 26/26 workers (60615 items) tests 7325 done 1 failed | 26 in flight, oldest 71s gw6 tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_return_row_text
............... [339%]
........................................................................ [342%]
...............................................[contention-diag] +1070s soak 28p/227t rss 10.9G pss 10.3G swap 1.0G majflt 2831 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G | host avail 33.5G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 33.73 | cgroup 10.7G/max oom_kill 0 | free scratch 304.9G/45115058i tmp 29.7G/1015654i workspace 304.9G/45115058i | repeat-01 collected 26/26 workers (60615 items) tests 7461 done 1 failed | 26 in flight, oldest 42s gw21 tests/ace/tui/test_help_modal_filter.py::test_slash_opens_and_focuses_filter_bar
......................... [345%]
........................................................................ [349%]
..............................[contention-diag] +1085s soak 28p/235t rss 11.0G pss 10.3G swap 1.0G majflt 2832 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G | host avail 36.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 36.89 | cgroup 10.7G/max oom_kill 0 | free scratch 304.9G/45114646i tmp 29.7G/1015654i workspace 304.9G/45114646i | repeat-01 collected 26/26 workers (60615 items) tests 7589 done 1 failed | 26 in flight, oldest 56s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
.......................................... [352%]
........................................................................ [355%]
................[contention-diag] +1100s soak 38p/276t rss 11.1G pss 10.3G swap 1.0G majflt 2832 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 36.9G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 51.45 | cgroup 10.8G/max oom_kill 0 | free scratch 304.9G/45114243i tmp 29.7G/1015654i workspace 304.9G/45114243i | scratch used 0.2G in 25558 entries | repeat-01 collected 26/26 workers (60615 items) tests 7716 done 1 failed | 26 in flight, oldest 71s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
..................[contention-diag] +1116s soak 38p/270t rss 11.1G pss 10.3G swap 1.0G majflt 2832 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.1G, 10 descendant rss 0.1G pss 0.0G | host avail 36.0G/62.7G swapfree 54.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.32 cpu 35.55 | cgroup 10.8G/max oom_kill 0 | free scratch 304.8G/45112924i tmp 29.7G/1015654i workspace 304.8G/45112924i | repeat-01 collected 26/26 workers (60615 items) tests 7738 done 1 failed | 26 in flight, oldest 87s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
...........................[contention-diag] +1131s soak 39p/285t rss 11.1G pss 10.4G swap 1.0G majflt 2832 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.8G pss 10.2G, 11 descendant rss 0.1G pss 0.0G | host avail 38.5G/62.7G swapfree 55.8G/64.0G oom_kill +0 | psi10 mem 0.49/0.49 io 0.08 cpu 26.24 | cgroup 10.8G/max oom_kill 0 | free scratch 304.8G/45113748i tmp 29.7G/1015654i workspace 304.8G/45113748i | repeat-01 collected 26/26 workers (60615 items) tests 7765 done 1 failed | 26 in flight, oldest 102s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
........... [359%]
............................[contention-diag] +1146s soak 38p/267t rss 11.1G pss 10.4G swap 1.0G majflt 2832 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 35.2G/62.7G swapfree 55.8G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 0.49 cpu 16.76 | cgroup 10.8G/max oom_kill 0 | free scratch 305.1G/45131539i tmp 29.7G/1015654i workspace 305.1G/45131540i | repeat-01 collected 26/26 workers (60615 items) tests 7801 done 1 failed | 26 in flight, oldest 117s gw19 tests/ace/tui/test_link_follow_bounded_panes.py::test_open_plans_does_not_leak_empty_project_choices
............................................ [362%]
....................................[contention-diag] +1162s soak 30p/239t rss 11.1G pss 10.4G swap 1.0G majflt 2832 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 2 descendant rss 0.0G pss 0.0G | host avail 33.9G/62.7G swapfree 55.8G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.39 cpu 10.94 | cgroup 10.8G/max oom_kill 0 | free scratch 304.5G/45139835i tmp 29.7G/1015654i workspace 304.5G/45139835i | repeat-01 collected 26/26 workers (60615 items) tests 7881 done 1 failed | 26 in flight, oldest 65s gw7 tests/ace/tui/test_agents_tab_x_clan_race_e2e.py::test_clan_x_stays_removed_through_racing_load_fleet_refresh_and_reload
.......................[contention-diag] +1177s soak 38p/275t rss 11.2G pss 10.4G swap 1.0G majflt 2832 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 32.6G/62.7G swapfree 55.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 15.52 | cgroup 10.9G/max oom_kill 0 | free scratch 304.4G/45137367i tmp 29.7G/1015654i workspace 304.4G/45137367i | repeat-01 collected 26/26 workers (60615 items) tests 7907 done 1 failed | 26 in flight, oldest 73s gw22 tests/ace/tui/test_artifacts_current_project_scope.py::test_startup_save_persists_pre_seed_query
............. [365%]
........................................................................ [369%]
...........................[contention-diag] +1192s soak 38p/267t rss 11.2G pss 10.4G swap 1.0G majflt 2838 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 30.7G/62.7G swapfree 55.8G/64.0G oom_kill +0 | psi10 mem 0.12/0.12 io 0.18 cpu 15.72 | cgroup 10.9G/max oom_kill 0 | free scratch 304.4G/45123242i tmp 29.7G/1015654i workspace 304.4G/45123242i | repeat-01 collected 26/26 workers (60615 items) tests 8015 done 1 failed | 26 in flight, oldest 61s gw3 tests/ace/tui/test_artifacts_limit_keys.py::test_artifacts_prompt_bar_ctrl_k_still_opens_history
..........................................[contention-diag] +1207s soak 38p/259t rss 11.2G pss 10.4G swap 1.0G majflt 2849 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.2G, 10 descendant rss 0.1G pss 0.0G | host avail 29.1G/62.7G swapfree 56.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.02 io 0.55 cpu 14.69 | cgroup 10.9G/max oom_kill 0 | free scratch 304.3G/45118483i tmp 29.7G/1015654i workspace 304.3G/45118483i | repeat-01 collected 26/26 workers (60615 items) tests 8061 done 1 failed | 26 in flight, oldest 74s gw11 tests/ace/tui/test_agents_node_rail_wiring.py::test_zoom_then_split_key_clears_hidden_class_and_shows_container
... [372%]
...........[contention-diag] +1223s soak 30p/235t rss 11.1G pss 10.4G swap 1.0G majflt 2849 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 10.9G pss 10.3G, 2 descendant rss 0.0G pss 0.0G | host avail 29.2G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.25 cpu 17.88 | cgroup 10.9G/max oom_kill 0 | free scratch 304.3G/45118323i tmp 29.7G/1015654i workspace 304.3G/45118323i | scratch used 0.2G in 27282 entries | repeat-01 collected 26/26 workers (60615 items) tests 8075 done 1 failed | 26 in flight, oldest 67s gw2 tests/ace/tui/test_agents_deck_picker.py::test_agents_pp_after_tools_returns_to_main_then_tools
............................................................. [375%]
......................................................................[contention-diag] +1238s soak 28p/235t rss 11.1G pss 10.4G swap 0.9G majflt 2856 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 27.3G/62.7G swapfree 56.1G/64.0G oom_kill +0 | psi10 mem 0.06/0.06 io 0.05 cpu 16.34 | cgroup 10.9G/max oom_kill 0 | free scratch 304.1G/45117898i tmp 29.7G/1015654i workspace 304.1G/45117898i | repeat-01 collected 26/26 workers (60615 items) tests 8192 done 1 failed | 25 in flight, oldest 45s gw8 tests/ace/tui/test_plugins_browser_pane_agent_clis.py::test_updates_hints_omit_scope_navigation
.. [379%]
..................................................................[contention-diag] +1254s soak 28p/249t rss 11.2G pss 10.5G swap 0.9G majflt 2856 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 30.2G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 0.1 cpu 15.54 | cgroup 10.9G/max oom_kill 0 | free scratch 302.8G/45117560i tmp 29.7G/1015654i workspace 302.8G/45117560i | repeat-01 collected 26/26 workers (60615 items) tests 8274 done 1 failed | 26 in flight, oldest 44s gw24 tests/ace/tui/test_main_deck_reply_steal_recovery.py::test_landed_reply_survives_same_subject_context_redelivery
...... [382%]
.................................................................[contention-diag] +1269s soak 28p/243t rss 11.2G pss 10.5G swap 0.9G majflt 2856 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G | host avail 30.9G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 18.71 | cgroup 10.9G/max oom_kill 0 | free scratch 302.9G/45117321i tmp 29.7G/1015654i workspace 302.9G/45117321i | repeat-01 collected 26/26 workers (60615 items) tests 8345 done 1 failed | 26 in flight, oldest 59s gw24 tests/ace/tui/test_main_deck_reply_steal_recovery.py::test_landed_reply_survives_same_subject_context_redelivery
....... [385%]
........................................................................ [389%]
........................................................................ [392%]
....................................[contention-diag] +1284s soak 29p/248t rss 11.2G pss 10.5G swap 0.9G majflt 3016 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 31.4G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 18.87 | cgroup 11.0G/max oom_kill 0 | free scratch 302.9G/45116875i tmp 29.7G/1015654i workspace 302.9G/45116875i | repeat-01 collected 26/26 workers (60615 items) tests 8531 done 1 failed | 26 in flight, oldest 74s gw4 tests/ace/tui/test_artifacts_list_navigation.py::test_plans_fast_navigation_skips_document_section_headings
.................................... [395%]
........................................................................ [399%]
........................................................................ [402%]
[contention-diag] +1300s soak 29p/211t rss 11.2G pss 10.5G swap 0.9G majflt 3112 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.0G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 31.4G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.53 | cgroup 11.0G/max oom_kill 0 | free scratch 302.9G/45116377i tmp 29.7G/1015654i workspace 302.9G/45116377i | repeat-01 collected 26/26 workers (60615 items) tests 8703 done 1 failed | 26 in flight, oldest 88s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........................................................................ [405%]
........................................................................ [409%]
........................................................................ [412%]
.............................................[contention-diag] +1315s soak 29p/224t rss 11.3G pss 10.6G swap 0.9G majflt 3003 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 31.9G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.08 | cgroup 11.0G/max oom_kill 0 | free scratch 302.9G/45115553i tmp 29.7G/1015654i workspace 302.9G/45115552i | repeat-01 collected 26/26 workers (60615 items) tests 8968 done 1 failed | 26 in flight, oldest 103s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
........................... [415%]
....[contention-diag] +1330s soak 28p/253t rss 11.3G pss 10.5G swap 0.9G majflt 3003 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G | host avail 32.9G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 24.65 | cgroup 11.0G/max oom_kill 0 | free scratch 302.8G/45115361i tmp 29.7G/1015654i workspace 302.8G/45115361i | repeat-01 collected 26/26 workers (60615 items) tests 9003 done 1 failed | 26 in flight, oldest 118s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.................................................................... [419%]
.................[contention-diag] +1345s soak 29p/262t rss 11.3G pss 10.6G swap 0.9G majflt 3014 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 33.7G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.09 cpu 27.95 | cgroup 11.1G/max oom_kill 0 | free scratch 302.8G/45115063i tmp 29.7G/1015654i workspace 302.8G/45115063i | scratch used 0.2G in 30224 entries | repeat-01 collected 26/26 workers (60615 items) tests 9085 done 1 failed | 26 in flight, oldest 133s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
....................................................... [422%]
..............................[contention-diag] +1361s soak 29p/251t rss 11.3G pss 10.6G swap 0.9G majflt 3014 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.1G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 33.9G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 35.1 | cgroup 11.1G/max oom_kill 0 | free scratch 302.8G/45114797i tmp 29.7G/1015654i workspace 302.8G/45114797i | repeat-01 collected 26/26 workers (60615 items) tests 9173 done 1 failed | 26 in flight, oldest 149s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
.......................................... [425%]
............[contention-diag] +1376s soak 29p/262t rss 11.4G pss 10.6G swap 0.9G majflt 3014 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 33.4G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 32.82 | cgroup 11.1G/max oom_kill 0 | free scratch 302.8G/45114542i tmp 29.7G/1015654i workspace 302.8G/45114542i | repeat-01 collected 26/26 workers (60615 items) tests 9226 done 1 failed | 26 in flight, oldest 164s gw13 tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
............................[contention-diag] +1392s soak 29p/252t rss 11.4G pss 10.6G swap 0.9G majflt 3025 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 32.8G/62.7G swapfree 56.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.96 | cgroup 11.2G/max oom_kill 0 | free scratch 302.8G/45114294i tmp 29.7G/1015654i workspace 302.8G/45114294i | repeat-01 collected 26/26 workers (60615 items) tests 9254 done 1 failed | 26 in flight, oldest 105s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................................ [429%]
...[contention-diag] +1407s soak 29p/249t rss 11.4G pss 10.7G swap 0.9G majflt 3025 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 56.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.09 | cgroup 11.2G/max oom_kill 0 | free scratch 302.9G/45114133i tmp 29.7G/1015654i workspace 302.9G/45114133i | repeat-01 collected 26/26 workers (60615 items) tests 9290 done 1 failed | 26 in flight, oldest 121s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
..................................................................[contention-diag] +1422s soak 28p/246t rss 11.4G pss 10.7G swap 0.9G majflt 3034 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 31.8G/62.7G swapfree 56.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.67 cpu 21.63 | cgroup 11.2G/max oom_kill 0 | free scratch 302.8G/45113508i tmp 29.7G/1015654i workspace 302.8G/45113508i | repeat-01 collected 26/26 workers (60615 items) tests 9357 done 1 failed | 26 in flight, oldest 136s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
... [432%]
........................................................................ [435%]
....[contention-diag] +1438s soak 29p/243t rss 11.4G pss 10.7G swap 0.9G majflt 3037 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 32.2G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.42 cpu 21.96 | cgroup 11.2G/max oom_kill 0 | free scratch 305.5G/45115574i tmp 29.7G/1015654i workspace 305.5G/45115574i | repeat-01 collected 26/26 workers (60615 items) tests 9433 done 1 failed | 26 in flight, oldest 151s gw3 tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
................................................[contention-diag] +1453s soak 28p/215t rss 11.4G pss 10.7G swap 0.9G majflt 3071 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G | host avail 32.3G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.1 cpu 23.11 | cgroup 11.2G/max oom_kill 0 | free scratch 305.5G/45115279i tmp 29.7G/1015651i workspace 305.5G/45115279i | repeat-01 collected 26/26 workers (60615 items) tests 9477 done 1 failed | 26 in flight, oldest 58s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_escape_escalates_insert_normal_browse_close_with_draft_intact
.................... [438%]
........................................................................ [442%]
............................................[contention-diag] +1468s soak 29p/246t rss 11.5G pss 10.8G swap 0.9G majflt 3077 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 30.1G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 0.16 cpu 19.88 | cgroup 11.3G/max oom_kill 0 | free scratch 305.3G/45113780i tmp 29.7G/1015654i workspace 305.3G/45113780i | scratch used 0.2G in 32232 entries | repeat-01 collected 26/26 workers (60615 items) tests 9612 done 1 failed | 25 in flight, oldest 58s gw21 tests/ace/tui/test_help_modal_filter.py::test_filter_persists_across_ace_tab_switch
............................ [445%]
........................................................................ [448%]
........................................[contention-diag] +1484s soak 29p/259t rss 11.4G pss 10.7G swap 0.9G majflt 3077 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.2G pss 10.5G, 1 descendant rss 0.0G pss 0.0G | host avail 30.2G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 16.03 | cgroup 11.3G/max oom_kill 0 | free scratch 304.8G/45112361i tmp 29.7G/1015654i workspace 304.8G/45112361i | repeat-01 collected 26/26 workers (60615 items) tests 9755 done 1 failed | 26 in flight, oldest 67s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................................ [452%]
[contention-diag] +1499s soak 29p/250t rss 11.6G pss 10.9G swap 0.9G majflt 3096 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.1G pss 0.1G | host avail 28.5G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 20.41 | cgroup 11.4G/max oom_kill 0 | free scratch 304.8G/45112267i tmp 29.7G/1015654i workspace 304.8G/45112267i | repeat-01 collected 26/26 workers (60615 items) tests 9789 done 1 failed | 26 in flight, oldest 82s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
......................................................................[contention-diag] +1515s soak 28p/232t rss 11.5G pss 10.7G swap 0.9G majflt 3104 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 27.5G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.55 cpu 19.67 | cgroup 11.3G/max oom_kill 0 | free scratch 304.8G/45112016i tmp 29.7G/1015654i workspace 304.8G/45112016i | repeat-01 collected 26/26 workers (60615 items) tests 9862 done 1 failed | 26 in flight, oldest 98s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.. [455%]
........................................................................ [458%]
.....................[contention-diag] +1530s soak 28p/234t rss 11.5G pss 10.8G swap 0.9G majflt 3105 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 29.1G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.11 cpu 19.95 | cgroup 11.3G/max oom_kill 0 | free scratch 304.8G/45111730i tmp 29.7G/1015654i workspace 304.8G/45111730i | repeat-01 collected 26/26 workers (60615 items) tests 9944 done 1 failed | 26 in flight, oldest 113s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................................[contention-diag] +1545s soak 29p/240t rss 11.5G pss 10.8G swap 0.9G majflt 3120 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 26.8G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 18.85 | cgroup 11.4G/max oom_kill 0 | free scratch 304.7G/45111556i tmp 29.7G/1015654i workspace 304.7G/45111556i | repeat-01 collected 26/26 workers (60615 items) tests 10006 done 1 failed | 26 in flight, oldest 128s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
. [462%]
........................................................................ [465%]
..................................................[contention-diag] +1561s soak 28p/252t rss 11.5G pss 10.8G swap 0.9G majflt 3145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 25.3G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 18.73 | cgroup 11.4G/max oom_kill 0 | free scratch 304.8G/45111126i tmp 29.7G/1015654i workspace 304.8G/45111126i | repeat-01 collected 26/26 workers (60615 items) tests 10130 done 1 failed | 26 in flight, oldest 144s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................... [468%]
[contention-diag] +1576s soak 28p/264t rss 11.5G pss 10.8G swap 0.9G majflt 3189 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G | host avail 25.0G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.77 | cgroup 11.4G/max oom_kill 0 | free scratch 304.8G/45110988i tmp 29.7G/1015654i workspace 304.8G/45110988i | repeat-01 collected 26/26 workers (60615 items) tests 10150 done 1 failed | 26 in flight, oldest 159s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................[contention-diag] +1592s soak 29p/253t rss 11.5G pss 10.8G swap 0.9G majflt 3189 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.3G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 25.7G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.47 | cgroup 11.4G/max oom_kill 0 | free scratch 304.5G/45110747i tmp 29.7G/1015654i workspace 304.5G/45110747i | scratch used 0.2G in 34228 entries | repeat-01 collected 26/26 workers (60615 items) tests 10168 done 1 failed | 26 in flight, oldest 174s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................................... [472%]
..[contention-diag] +1607s soak 29p/267t rss 11.6G pss 10.9G swap 0.9G majflt 3189 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.6G, 1 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 22.11 | cgroup 11.4G/max oom_kill 0 | free scratch 304.5G/45110500i tmp 29.7G/1015654i workspace 304.5G/45110500i | repeat-01 collected 26/26 workers (60615 items) tests 10219 done 1 failed | 26 in flight, oldest 190s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
...................................................................... [475%]
...................................[contention-diag] +1622s soak 28p/258t rss 11.6G pss 10.8G swap 0.9G majflt 3189 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 29.6G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 26.43 | cgroup 11.5G/max oom_kill 0 | free scratch 304.5G/45110191i tmp 29.7G/1015654i workspace 304.5G/45110191i | repeat-01 collected 26/26 workers (60615 items) tests 10327 done 1 failed | 26 in flight, oldest 205s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
..................................... [478%]
............................................................[contention-diag] +1638s soak 30p/248t rss 11.7G pss 10.9G swap 0.9G majflt 3190 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.1G pss 0.1G | host avail 31.7G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.49 | cgroup 11.6G/max oom_kill 0 | free scratch 304.4G/45109819i tmp 29.7G/1015654i workspace 304.4G/45109819i | repeat-01 collected 26/26 workers (60615 items) tests 10426 done 1 failed | 26 in flight, oldest 221s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
............ [482%]
.......................................................[contention-diag] +1653s soak 32p/270t rss 11.6G pss 10.9G swap 0.9G majflt 3190 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 4 descendant rss 0.0G pss 0.0G | host avail 31.3G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 28.83 | cgroup 11.5G/max oom_kill 0 | free scratch 304.4G/45109506i tmp 29.7G/1015654i workspace 304.4G/45109506i | repeat-01 collected 26/26 workers (60615 items) tests 10494 done 1 failed | 26 in flight, oldest 236s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
................. [485%]
........................................................................ [488%]
........................................................................ [492%]
......................[contention-diag] +1668s soak 28p/257t rss 11.6G pss 10.9G swap 0.9G majflt 3196 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G | host avail 29.8G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 29.29 | cgroup 11.5G/max oom_kill 0 | free scratch 304.4G/45108918i tmp 29.7G/1015654i workspace 304.4G/45108918i | repeat-01 collected 26/26 workers (60615 items) tests 10675 done 1 failed | 26 in flight, oldest 251s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................................................. [495%]
......................................................[contention-diag] +1684s soak 29p/271t rss 11.6G pss 10.9G swap 0.9G majflt 3206 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 1 descendant rss 0.0G pss 0.0G | host avail 31.8G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 25.14 | cgroup 11.5G/max oom_kill 0 | free scratch 304.4G/45108590i tmp 29.7G/1015654i workspace 304.4G/45108590i | repeat-01 collected 26/26 workers (60615 items) tests 10779 done 1 failed | 26 in flight, oldest 267s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.................. [498%]
........................................................................ [502%]
.[contention-diag] +1699s soak 30p/254t rss 11.7G pss 10.9G swap 0.9G majflt 3212 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 30.4G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.05 cpu 22.79 | cgroup 11.6G/max oom_kill 0 | free scratch 304.4G/45108290i tmp 29.7G/1015654i workspace 304.4G/45108290i | repeat-01 collected 26/26 workers (60615 items) tests 10870 done 1 failed | 26 in flight, oldest 282s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.............................[contention-diag] +1714s soak 31p/265t rss 11.6G pss 10.9G swap 0.9G majflt 3227 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 3 descendant rss 0.0G pss 0.0G | host avail 29.7G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.27 cpu 24.67 | cgroup 11.5G/max oom_kill 0 | free scratch 304.4G/45108063i tmp 29.7G/1015654i workspace 304.4G/45108063i | scratch used 0.2G in 36750 entries | repeat-01 collected 26/26 workers (60615 items) tests 10899 done 1 failed | 26 in flight, oldest 297s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.......................................... [505%]
......................................................................[contention-diag] +1730s soak 30p/274t rss 11.7G pss 10.9G swap 0.9G majflt 3238 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 29.7G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.16 cpu 26.59 | cgroup 11.6G/max oom_kill 0 | free scratch 304.4G/45107623i tmp 29.7G/1015654i workspace 304.4G/45107623i | repeat-01 collected 26/26 workers (60615 items) tests 11009 done 1 failed | 26 in flight, oldest 313s gw6 tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
.. [508%]
.......................[contention-diag] +1745s soak 30p/283t rss 11.7G pss 10.9G swap 0.9G majflt 3258 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 30.0G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 28.04 | cgroup 11.6G/max oom_kill 0 | free scratch 304.4G/45107379i tmp 29.7G/1015654i workspace 304.4G/45107379i | repeat-01 collected 26/26 workers (60615 items) tests 11037 done 1 failed | 26 in flight, oldest 59s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
.....[contention-diag] +1760s soak 30p/292t rss 11.7G pss 10.9G swap 0.9G majflt 3258 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.7G, 2 descendant rss 0.0G pss 0.0G | host avail 29.7G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 24.88 | cgroup 11.6G/max oom_kill 0 | free scratch 304.4G/45107263i tmp 29.7G/1015654i workspace 304.4G/45107263i | repeat-01 collected 26/26 workers (60615 items) tests 11044 done 1 failed | 26 in flight, oldest 74s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
............................................ [512%]
.................................................................[contention-diag] +1776s soak 32p/289t rss 11.8G pss 11.0G swap 0.8G majflt 3281 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 4 descendant rss 0.1G pss 0.1G | host avail 26.4G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.66 | cgroup 11.7G/max oom_kill 0 | free scratch 304.4G/45106986i tmp 29.7G/1015654i workspace 304.4G/45106986i | repeat-01 collected 26/26 workers (60615 items) tests 11149 done 1 failed | 26 in flight, oldest 89s gw2 tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
....... [515%]
........................................................................ [518%]
........................................................................ [522%]
........................................................................ [525%]
................................[contention-diag] +1791s soak 29p/269t rss 11.7G pss 11.0G swap 0.8G majflt 3281 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 25.2G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.36 cpu 18.99 | cgroup 11.7G/max oom_kill 0 | free scratch 304.4G/45106247i tmp 29.7G/1015654i workspace 304.4G/45106247i | repeat-01 collected 26/26 workers (60615 items) tests 11402 done 1 failed | 26 in flight, oldest 51s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_required_description_cannot_be_cleared
........................................ [528%]
.........................................................[contention-diag] +1806s soak 29p/261t rss 11.8G pss 11.0G swap 0.8G majflt 3316 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 1 descendant rss 0.1G pss 0.1G | host avail 26.8G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.07 cpu 14.61 | cgroup 11.7G/max oom_kill 0 | free scratch 304.0G/45103791i tmp 29.7G/1015654i workspace 304.0G/45103791i | repeat-01 collected 26/26 workers (60615 items) tests 11499 done 1 failed | 26 in flight, oldest 65s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
............... [532%]
.......[contention-diag] +1822s soak 31p/278t rss 11.8G pss 11.1G swap 0.8G majflt 3287 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.8G, 3 descendant rss 0.1G pss 0.1G | host avail 25.5G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 16.28 | cgroup 11.8G/max oom_kill 0 | free scratch 303.9G/45103488i tmp 29.7G/1015654i workspace 303.9G/45103488i | repeat-01 collected 26/26 workers (60615 items) tests 11526 done 1 failed | 26 in flight, oldest 80s gw4 tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_perf_harness_records_space_and_cycle
................................................................. [535%]
.....[contention-diag] +1837s soak 29p/253t rss 11.8G pss 11.1G swap 0.8G majflt 3286 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 21.3G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.29 cpu 11.38 | cgroup 11.8G/max oom_kill 0 | free scratch 303.7G/45103087i tmp 29.7G/1015654i workspace 303.7G/45103087i | scratch used 0.2G in 39337 entries | repeat-01 collected 26/26 workers (60615 items) tests 11594 done 1 failed | 26 in flight, oldest 54s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_ctrl_i_loads_non_yaml_macro_into_prompt_bar
.........................[contention-diag] +1853s soak 29p/261t rss 11.8G pss 11.0G swap 0.8G majflt 3286 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.8G, 1 descendant rss 0.0G pss 0.0G | host avail 14.3G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.48/0.31 io 0.05 cpu 8.13 | cgroup 11.6G/max oom_kill 0 | free scratch 304.1G/45107741i tmp 29.7G/1015654i workspace 304.1G/45107741i | repeat-01 collected 26/26 workers (60615 items) tests 11619 done 1 failed | 26 in flight, oldest 61s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_plugins_pane_summary_counts
.................................[contention-diag] +1869s soak 30p/263t rss 11.9G pss 11.1G swap 0.9G majflt 3416 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.8G, 2 descendant rss 0.1G pss 0.1G | host avail 13.6G/62.7G swapfree 58.2G/64.0G oom_kill +0 | psi10 mem 0.09/0.06 io 0.31 cpu 7.28 | cgroup 11.7G/max oom_kill 0 | free scratch 304.0G/45107453i tmp 29.7G/1015654i workspace 304.0G/45107453i | repeat-01 collected 26/26 workers (60615 items) tests 11652 done 1 failed | 25 in flight, oldest 70s gw23 tests/ace/tui/test_feature_flags_pane_journeys.py::test_flags_pane_enable_and_disable_write_state_and_request_restart
......... [538%]
...........[contention-diag] +1884s soak 31p/270t rss 11.6G pss 10.7G swap 1.3G majflt 3483 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.4G pss 10.5G, 3 descendant rss 0.1G pss 0.1G | host avail 8.0G/62.7G swapfree 57.0G/64.0G oom_kill +0 | psi10 mem 5.97/4.43 io 5.31 cpu 7.19 | cgroup 11.0G/max oom_kill 0 | free scratch 304.0G/45107348i tmp 29.7G/1015654i workspace 304.0G/45107348i | repeat-01 collected 26/26 workers (60615 items) tests 11674 done 1 failed | 26 in flight, oldest 69s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
..F[contention-failure] call tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_preserves_collapsed_sections: monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f2350d47650>

    async def test_config_jump_preserves_collapsed_sections(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_jump.py:127: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:330: in __aenter__
    await settle_helpers.settle_pilot(self._pilot)
src/sase/ace/testing/settle.py:43: in settle_pilot
    await pause(pilot, 0)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/pilot.py:530: in pause
    await self._wait_for_screen()
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Pilot app=AceApp(title='sase tui (v0.18.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})>
timeout = 30.0

    async def _wait_for_screen(self, timeout: float = 30.0) -> bool:
        """Wait for the current screen and its children to have processed all pending events.
    
        Args:
            timeout: A timeout in seconds to wait.
    
        Returns:
            `True` if all events were processed. `False` if an exception occurred,
            meaning that not all events could be processed.
    
        Raises:
            WaitForScreenTimeout: If the screen and its children didn't finish processing within the timeout.
        """
        try:
            screen = self.app.screen
        except Exception:
            return False
        children = [self.app, *screen.walk_children(with_self=True)]
        count = 0
        count_zero_event = asyncio.Event()
    
        def decrement_counter() -> None:
            """Decrement internal counter, and set an event if it reaches zero."""
            nonlocal count
            count -= 1
            if count == 0:
                # When count is zero, all messages queued at the start of the method have been processed
                count_zero_event.set()
    
        # Increase the count for every successful call_later
        for child in children:
            if child.call_later(decrement_counter):
                count += 1
    
        if count:
            # Wait for the count to return to zero, or a timeout, or an exception
            wait_for = [
                asyncio.create_task(count_zero_event.wait()),
                asyncio.create_task(self.app._exception_event.wait()),
            ]
            _, pending = await asyncio.wait(
                wait_for,
                timeout=timeout,
                return_when=asyncio.FIRST_COMPLETED,
            )
    
            for task in pending:
                task.cancel()
    
            timed_out = len(wait_for) == len(pending)
            if timed_out:
>               raise WaitForScreenTimeout(
                    "Timed out while waiting for widgets to process pending messages."
                )
E           
.............................................F[contention-failure] call tests/ace/tui/test_gate_input_panel_layout.py::test_tab_reaches_every_field_and_scrolls_it_into_view: async def test_tab_reaches_every_field_and_scrolls_it_into_view() -> None:
        request = _tall_request()
        panel = GateInputPanel(request)
        app = StyledGateTestApp()
        async with app.run_test(size=(120, 40)) as pilot:
            app.push_screen(panel)
>           await _wait_for_panel(pilot, 120, 40, panel)

tests/ace/tui/test_gate_input_panel_layout.py:123: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/test_gate_input_panel_layout.py:77: in _wait_for_panel
    await wait_for_terminal(pilot, width, height)
tests/ace/tui/_custom_gate_modal_helpers.py:134: in wait_for_terminal
    await wait_for(pilot, terminal_matches)
src/sase/ace/testing/wait.py:98: in wait_for
    await _poll_until(
src/sase/ace/testing/wait.py:66: in _poll_until
    await settle()
src/sase/ace/testing/settle.py:43: in settle_pilot
    await pause(pilot, 0)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/pilot.py:530: in pause
    await self._wait_for_screen()
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Pilot app=StyledGateTestApp(title='StyledGateTestApp', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})>
timeout = 30.0

    async def _wait_for_screen(self, timeout: float = 30.0) -> bool:
        """Wait for the current screen and its children to have processed all pending events.
    
        Args:
            timeout: A timeout in seconds to wait.
    
        Returns:
            `True` if all events were processed. `False` if an exception occurred,
            meaning that not all events could be processed.
    
        Raises:
            WaitForScreenTimeout: If the screen and its children didn't finish processing within the timeout.
        """
        try:
            screen = self.app.screen
        except Exception:
            return False
        children = [self.app, *screen.walk_children(with_self=True)]
        count = 0
        count_zero_event = asyncio.Event()
    
        def decrement_counter() -> None:
            """Decrement internal counter, and set an event if it reaches zero."""
            nonlocal count
            count -= 1
            if count == 0:
                # When count is zero, all messages queued at the start of the method have been processed
                count_zero_event.set()
    
        # Increase the count for every successful call_later
        for child in children:
            if child.call_later(decrement_counter):
                count += 1
    
        if count:
            # Wait for the count to return to zero, or a timeout, or an exception
            wait_for = [
                asyncio.create_task(count_zero_event.wait()),
                asyncio.create_task(self.app._exception_event.wait()),
            ]
            _, pending = await asyncio.wait(
                wait_for,
                timeout=timeout,
                return_when=asyncio.FIRST_COMPLETED,
            )

............ [542%]
.................[contention-diag] +1900s soak 30p/268t rss 11.4G pss 10.3G swap 1.6G majflt 5549 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.2G, 2 descendant rss 0.0G pss 0.0G | host avail 7.1G/62.7G swapfree 53.4G/64.0G oom_kill +0 | psi10 mem 41.1/36.58 io 43.18 cpu 5.82 | cgroup 10.5G/max oom_kill 0 | free scratch 304.0G/45107151i tmp 29.7G/1015654i workspace 304.0G/45107151i | repeat-01 collected 26/26 workers (60615 items) tests 11742 done 3 failed | 26 in flight, oldest 85s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
........................[contention-diag] +1915s soak 31p/277t rss 11.2G pss 10.1G swap 1.9G majflt 11926 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.0G, 3 descendant rss 0.1G pss 0.1G | host avail 6.5G/62.7G swapfree 50.2G/64.0G oom_kill +0 | psi10 mem 50.83/45.25 io 54.07 cpu 5.33 | cgroup 10.3G/max oom_kill 0 | free scratch 304.0G/45106965i tmp 29.7G/1015653i workspace 304.0G/45106965i | repeat-01 collected 26/26 workers (60615 items) tests 11774 done 3 failed | 26 in flight, oldest 100s gw9 tests/ace/tui/test_projects_pane.py::test_admin_center_reaches_projects_tab_from_config
............................... [545%]
...................[contention-diag] +1930s soak 31p/268t rss 11.0G pss 9.9G swap 2.2G majflt 42868 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.8G pss 9.8G, 3 descendant rss 0.1G pss 0.1G | host avail 8.9G/62.7G swapfree 48.1G/64.0G oom_kill +0 | psi10 mem 24.7/20.55 io 43.62 cpu 6.08 | cgroup 10.1G/max oom_kill 0 | free scratch 303.7G/45106812i tmp 29.7G/1015654i workspace 303.7G/45106812i | repeat-01 collected 26/26 workers (60615 items) tests 11824 done 3 failed | 26 in flight, oldest 71s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
..................................................... [548%]
.[contention-diag] +1946s soak 31p/262t rss 11.1G pss 10.0G swap 2.1G majflt 55504 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 10.9G pss 9.9G, 3 descendant rss 0.1G pss 0.1G | host avail 11.3G/62.7G swapfree 48.8G/64.0G oom_kill +0 | psi10 mem 5.83/4.74 io 13.1 cpu 7.33 | cgroup 10.2G/max oom_kill 0 | free scratch 304.0G/45106533i tmp 29.7G/1015654i workspace 304.0G/45106533i | repeat-01 collected 26/26 workers (60615 items) tests 11872 done 3 failed | 26 in flight, oldest 87s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
....................................................................... [552%]
..........................................[contention-diag] +1961s soak 30p/252t rss 11.1G pss 10.0G swap 2.0G majflt 55997 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.9G, 2 descendant rss 0.0G pss 0.0G | host avail 14.5G/62.7G swapfree 48.9G/64.0G oom_kill +0 | psi10 mem 1.98/0.95 io 3.07 cpu 9.1 | cgroup 10.2G/max oom_kill 0 | free scratch 304.4G/45111279i tmp 29.7G/1015654i workspace 304.4G/45111279i | scratch used 0.1G in 15666 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 11965 done 3 failed | 26 in flight, oldest 102s gw10 tests/ace/tui/test_axe_entry_editor_modal.py::test_stopped_save_and_running_save_only_never_request_restart
.............................. [555%]
........................................................................ [558%]
...........[contention-diag] +1979s soak 29p/243t rss 11.1G pss 10.0G swap 2.0G majflt 57464 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 14.3G/62.7G swapfree 49.0G/64.0G oom_kill +0 | psi10 mem 0.32/0.15 io 0.96 cpu 9.13 | cgroup 10.3G/max oom_kill 0 | free scratch 304.4G/45110721i tmp 29.7G/1015653i workspace 304.4G/45110721i | repeat-01 collected 26/26 workers (60615 items) tests 12101 done 3 failed | 26 in flight, oldest 51s gw5 tests/ace/tui/test_property_picker_modal.py::test_frontmatter_wrapper_retains_copy_and_dom_ids
......................................................[contention-diag] +1994s soak 30p/264t rss 11.2G pss 10.0G swap 2.1G majflt 58186 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.9G, 2 descendant rss 0.1G pss 0.1G | host avail 17.4G/62.7G swapfree 49.0G/64.0G oom_kill +0 | psi10 mem 0.07/0.03 io 0.41 cpu 10.06 | cgroup 10.3G/max oom_kill 0 | free scratch 304.4G/45110497i tmp 29.7G/1015653i workspace 304.4G/45110497i | repeat-01 collected 26/26 workers (60615 items) tests 12158 done 3 failed | 26 in flight, oldest 56s gw23 tests/ace/tui/test_link_follow_planner.py::test_phase_context_rewrite_selects_and_restores
....... [562%]
........................................................................ [565%]
........................................................................ [568%]
...................................[contention-diag] +2010s soak 29p/244t rss 11.1G pss 10.0G swap 2.0G majflt 59231 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 24.3G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.0 io 0.91 cpu 11.7 | cgroup 10.3G/max oom_kill 0 | free scratch 304.3G/45109906i tmp 29.7G/1015653i workspace 304.3G/45109906i | repeat-01 collected 26/26 workers (60615 items) tests 12343 done 3 failed | 26 in flight, oldest 71s gw23 tests/ace/tui/test_link_follow_planner.py::test_phase_context_rewrite_selects_and_restores
..................................... [572%]
........................................................................ [575%]
........................................................[contention-diag] +2025s soak 29p/249t rss 11.1G pss 10.0G swap 2.0G majflt 60185 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 9.9G, 1 descendant rss 0.0G pss 0.0G | host avail 22.3G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 12.81 | cgroup 10.3G/max oom_kill 0 | free scratch 304.8G/45107999i tmp 29.7G/1015653i workspace 304.8G/45107999i | repeat-01 collected 26/26 workers (60615 items) tests 12509 done 3 failed | 26 in flight, oldest 70s gw19 tests/ace/tui/test_statistics_pane_filters.py::test_group_cycle_is_view_sensitive_and_projects_reuses_result
................ [578%]
........................................................................ [581%]
.........................[contention-diag] +2040s soak 30p/257t rss 11.1G pss 10.0G swap 2.0G majflt 61937 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.0G pss 10.0G, 2 descendant rss 0.0G pss 0.0G | host avail 26.5G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.06 cpu 14.44 | cgroup 10.3G/max oom_kill 0 | free scratch 304.8G/45107657i tmp 29.7G/1015653i workspace 304.8G/45107657i | repeat-01 collected 26/26 workers (60615 items) tests 12614 done 3 failed | 26 in flight, oldest 62s gw2 tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_opens_preview_modal
............................................... [585%]
........................................................................ [588%]
....................[contention-diag] +2056s soak 31p/256t rss 11.2G pss 10.1G swap 2.0G majflt 67086 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.1G pss 10.0G, 3 descendant rss 0.0G pss 0.0G | host avail 25.7G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 12.29 | cgroup 10.4G/max oom_kill 0 | free scratch 304.8G/45107271i tmp 29.7G/1015652i workspace 304.8G/45107271i | repeat-01 collected 26/26 workers (60615 items) tests 12750 done 3 failed | 26 in flight, oldest 50s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
.................................................... [591%]
........................................................................ [595%]
........................................................................ [598%]
.............[contention-diag] +2071s soak 32p/262t rss 11.3G pss 10.1G swap 1.9G majflt 71139 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.1G pss 10.0G, 4 descendant rss 0.1G pss 0.0G | host avail 25.7G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.03 cpu 17.26 | cgroup 10.5G/max oom_kill 0 | free scratch 304.8G/45106842i tmp 29.7G/1015653i workspace 304.8G/45106842i | repeat-01 collected 26/26 workers (60615 items) tests 12970 done 3 failed | 26 in flight, oldest 65s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
........................................................... [601%]
........................................................................ [605%]
........................................................................ [608%]
...........................................[contention-diag] +2086s soak 31p/259t rss 11.3G pss 10.2G swap 1.9G majflt 73772 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.1G pss 10.1G, 3 descendant rss 0.1G pss 0.1G | host avail 25.5G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 19.46 | cgroup 10.7G/max oom_kill 0 | free scratch 304.8G/45106198i tmp 29.7G/1015653i workspace 304.8G/45106198i | scratch used 0.2G in 39376 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 13175 done 3 failed | 25 in flight, oldest 80s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_spare_mounts_idle_inert
............................. [611%]
...........................................[contention-diag] +2104s soak 29p/241t rss 11.3G pss 10.2G swap 1.9G majflt 74182 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.1G, 1 descendant rss 0.0G pss 0.0G | host avail 24.8G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.08 cpu 16.42 | cgroup 10.8G/max oom_kill 0 | free scratch 304.8G/45105742i tmp 29.7G/1015653i workspace 304.8G/45105742i | repeat-01 collected 26/26 workers (60615 items) tests 13289 done 3 failed | 26 in flight, oldest 42s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_plugins_pane_shows_update_marker
............................. [615%]
.............................................[contention-diag] +2119s soak 28p/245t rss 11.3G pss 10.2G swap 1.9G majflt 74992 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.1G | host avail 24.7G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.01 cpu 20.83 | cgroup 10.8G/max oom_kill 0 | free scratch 304.8G/45105430i tmp 29.7G/1015653i workspace 304.8G/45105430i | repeat-01 collected 26/26 workers (60615 items) tests 13359 done 3 failed | 26 in flight, oldest 53s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
........................... [618%]
.........................[contention-diag] +2134s soak 32p/263t rss 11.4G pss 10.3G swap 1.9G majflt 76998 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.1G, 4 descendant rss 0.1G pss 0.1G | host avail 22.0G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 17.11 | cgroup 11.0G/max oom_kill 0 | free scratch 304.6G/45105359i tmp 29.7G/1015653i workspace 304.6G/45105359i | repeat-01 collected 26/26 workers (60615 items) tests 13411 done 3 failed | 26 in flight, oldest 68s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............................................... [621%]
..............................[contention-diag] +2150s soak 32p/273t rss 11.5G pss 10.4G swap 1.8G majflt 79842 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.1G, 4 descendant rss 0.2G pss 0.2G | host avail 26.7G/62.7G swapfree 50.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 15.57 | cgroup 11.2G/max oom_kill 0 | free scratch 304.8G/45105035i tmp 29.7G/1015653i workspace 304.8G/45105035i | repeat-01 collected 26/26 workers (60615 items) tests 13492 done 3 failed | 26 in flight, oldest 83s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
.......................................... [625%]
........................[contention-diag] +2165s soak 35p/257t rss 11.5G pss 10.4G swap 1.8G majflt 75907 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.2G pss 10.2G, 7 descendant rss 0.2G pss 0.2G | host avail 29.4G/62.7G swapfree 50.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.0 cpu 21.6 | cgroup 11.3G/max oom_kill 0 | free scratch 304.8G/45104481i tmp 29.7G/1015653i workspace 304.8G/45104481i | repeat-01 collected 26/26 workers (60615 items) tests 13558 done 3 failed | 26 in flight, oldest 99s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
................................................ [628%]
.........................................[contention-diag] +2180s soak 30p/269t rss 11.4G pss 10.2G swap 1.8G majflt 76216 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.2G, 2 descendant rss 0.0G pss 0.0G | host avail 29.2G/62.7G swapfree 50.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.74 cpu 25.11 | cgroup 11.2G/max oom_kill 0 | free scratch 304.8G/45104188i tmp 29.7G/1015653i workspace 304.8G/45104188i | repeat-01 collected 26/26 workers (60615 items) tests 13644 done 3 failed | 26 in flight, oldest 114s gw11 tests/ace/tui/test_history_kit_door.py::test_ace_imports_history_presentation_only_through_kit
............................... [631%]
........................................................................ [635%]
.............................................[contention-diag] +2196s soak 28p/276t rss 11.4G pss 10.2G swap 1.8G majflt 77129 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.2G | host avail 28.3G/62.7G swapfree 50.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.19 cpu 23.8 | cgroup 11.3G/max oom_kill 0 | free scratch 304.8G/45103689i tmp 29.7G/1015653i workspace 304.8G/45103689i | repeat-01 collected 26/26 workers (60615 items) tests 13791 done 3 failed | 26 in flight, oldest 51s gw23 tests/ace/tui/test_link_follow_planner.py::test_task_context_preserves_small_limit
........................... [638%]
.......................................................................[contention-diag] +2211s soak 29p/268t rss 11.4G pss 10.3G swap 1.8G majflt 77440 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 27.6G/62.7G swapfree 50.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.04 cpu 23.25 | cgroup 11.4G/max oom_kill 0 | free scratch 304.8G/45103322i tmp 29.7G/1015651i workspace 304.8G/45103322i | scratch used 0.3G in 46982 entries | repeat-01 collected 26/26 workers (60615 items) tests 13880 done 3 failed | 26 in flight, oldest 65s gw21 tests/ace/tui/test_tribe_panel_flicker.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
. [641%]
........................................................................ [645%]
......................[contention-diag] +2227s soak 30p/275t rss 11.5G pss 10.4G swap 1.8G majflt 77755 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.2G, 2 descendant rss 0.1G pss 0.1G | host avail 27.6G/62.7G swapfree 50.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.74 cpu 23.49 | cgroup 11.5G/max oom_kill 0 | free scratch 304.8G/45102904i tmp 29.7G/1015653i workspace 304.8G/45102904i | repeat-01 collected 26/26 workers (60615 items) tests 13980 done 3 failed | 26 in flight, oldest 81s gw21 tests/ace/tui/test_tribe_panel_flicker.py::test_selected_tribe_noop_refresh_keeps_main_deck_stable
.................................................. [648%]
.................................................[contention-diag] +2242s soak 29p/274t rss 11.4G pss 10.3G swap 1.8G majflt 77920 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.2G, 1 descendant rss 0.0G pss 0.0G | host avail 26.2G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.14 cpu 13.19 | cgroup 11.6G/max oom_kill 0 | free scratch 304.3G/45100775i tmp 29.7G/1015653i workspace 304.3G/45100775i | repeat-01 collected 26/26 workers (60615 items) tests 14083 done 3 failed | 26 in flight, oldest 70s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_reveal_matches_fresh_home[pairs1-]
....................... [651%]
........................................................................ [655%]
........................................................................ [658%]
..................[contention-diag] +2258s soak 31p/255t rss 11.4G pss 10.3G swap 1.8G majflt 80054 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.2G, 3 descendant rss 0.0G pss 0.0G | host avail 27.1G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.02 cpu 18.48 | cgroup 11.5G/max oom_kill 0 | free scratch 304.1G/45099954i tmp 29.7G/1015653i workspace 304.1G/45099954i | repeat-01 collected 26/26 workers (60615 items) tests 14270 done 3 failed | 26 in flight, oldest 69s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
...................................................... [661%]
........................................................................ [665%]
.....................................[contention-diag] +2273s soak 32p/260t rss 11.5G pss 10.3G swap 1.8G majflt 80665 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 10.3G, 4 descendant rss 0.0G pss 0.0G | host avail 23.2G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.28 cpu 18.51 | cgroup 11.6G/max oom_kill 0 | free scratch 304.1G/45098864i tmp 29.7G/1015653i workspace 304.1G/45098864i | repeat-01 collected 26/26 workers (60615 items) tests 14436 done 3 failed | 26 in flight, oldest 84s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_final_worker_completion_keeps_ctrl_j_card
................................... [668%]
..........................................................[contention-diag] +2289s soak 31p/266t rss 11.5G pss 10.4G swap 1.8G majflt 81096 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 10.3G, 3 descendant rss 0.0G pss 0.0G | host avail 23.3G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.48 cpu 18.07 | cgroup 11.5G/max oom_kill 0 | free scratch 304.1G/45098457i tmp 29.7G/1015653i workspace 304.1G/45098457i | repeat-01 collected 26/26 workers (60615 items) tests 14529 done 3 failed | 26 in flight, oldest 64s gw16 tests/ace/tui/test_macro_browser_load_keymap.py::test_digits_type_in_an_opened_filter
.............. [671%]
............................................[contention-diag] +2304s soak 31p/282t rss 11.5G pss 10.4G swap 1.8G majflt 81356 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 10.3G, 3 descendant rss 0.0G pss 0.0G | host avail 21.0G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.21 cpu 19.14 | cgroup 11.5G/max oom_kill 0 | free scratch 304.1G/45098802i tmp 29.7G/1015653i workspace 304.1G/45098802i | repeat-01 collected 26/26 workers (60615 items) tests 14582 done 3 failed | 26 in flight, oldest 61s gw18 tests/ace/tui/test_plugins_browser_pane_agent_clis_install.py::test_install_task_failure_reports_unsuccessful
............................ [675%]
........................................................................ [678%]
......[contention-diag] +2320s soak 32p/254t rss 11.6G pss 10.5G swap 1.8G majflt 82182 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 10.3G, 4 descendant rss 0.1G pss 0.1G | host avail 19.2G/62.7G swapfree 50.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.44 cpu 17.94 | cgroup 11.6G/max oom_kill 0 | free scratch 304.1G/45097902i tmp 29.7G/1015653i workspace 304.1G/45097902i | repeat-01 collected 26/26 workers (60615 items) tests 14687 done 3 failed | 25 in flight, oldest 67s gw24 tests/ace/tui/test_prompt_bar_hot_spare.py::test_cold_late_prefill_lands_on_revealed_bar
.................................................................. [681%]
........................................................................ [685%]
........................................[contention-diag] +2335s soak 29p/245t rss 11.6G pss 10.5G swap 1.7G majflt 84629 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.5G pss 10.4G, 1 descendant rss 0.0G pss 0.0G | host avail 17.2G/62.7G swapfree 50.4G/64.0G oom_kill +0 | psi10 mem 0.09/0.09 io 1.5 cpu 14.89 | cgroup 11.6G/max oom_kill 0 | free scratch 304.1G/45096935i tmp 29.7G/1015651i workspace 304.1G/45096936i | scratch used 0.3G in 51231 entries | repeat-01 collected 26/26 workers (60615 items) tests 14849 done 3 failed | 26 in flight, oldest 56s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
................................ [688%]
........................................................................ [691%]
........................................................................ [695%]
........................................................................ [698%]
.....[contention-diag] +2351s soak 30p/263t rss 11.6G pss 10.5G swap 1.7G majflt 87799 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.5G pss 10.4G, 2 descendant rss 0.0G pss 0.0G | host avail 16.5G/62.7G swapfree 50.4G/64.0G oom_kill +0 | psi10 mem 0.24/0.24 io 2.11 cpu 13.33 | cgroup 11.6G/max oom_kill 0 | free scratch 304.0G/45095711i tmp 29.7G/1015651i workspace 304.0G/45095711i | repeat-01 collected 26/26 workers (60615 items) tests 15111 done 3 failed | 26 in flight, oldest 71s gw25 tests/ace/tui/widgets/decks/test_deck_card_choice_survives_repaint.py::test_record_worker_completion_keeps_ctrl_j_card
................................................................... [701%]
........................................................................ [705%]
.........................................[contention-diag] +2366s soak 32p/259t rss 11.7G pss 10.6G swap 1.7G majflt 95831 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.5G, 4 descendant rss 0.1G pss 0.0G | host avail 16.3G/62.7G swapfree 50.3G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.62 cpu 10.19 | cgroup 11.7G/max oom_kill 0 | free scratch 303.4G/45094603i tmp 29.7G/1015651i workspace 303.4G/45094603i | repeat-01 collected 26/26 workers (60615 items) tests 15302 done 3 failed | 26 in flight, oldest 69s gw20 tests/ace/tui/widgets/decks/test_deck_split_pilot.py::test_deck_close_each_and_erase_through_keys
............................... [708%]
..............................................................[contention-diag] +2381s soak 31p/271t rss 11.8G pss 10.7G swap 1.6G majflt 105160 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.7G pss 10.6G, 3 descendant rss 0.0G pss 0.0G | host avail 26.3G/62.7G swapfree 50.4G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 1.63 cpu 12.89 | cgroup 11.8G/max oom_kill 0 | free scratch 303.8G/45093808i tmp 29.7G/1015651i workspace 303.8G/45093808i | repeat-01 collected 26/26 workers (60615 items) tests 15395 done 3 failed | 26 in flight, oldest 72s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.......... [711%]
........................................................................ [715%]
....................[contention-diag] +2397s soak 34p/267t rss 12.0G pss 10.8G swap 1.6G majflt 105630 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.7G pss 10.6G, 6 descendant rss 0.2G pss 0.1G | host avail 24.2G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.93 cpu 13.14 | cgroup 12.1G/max oom_kill 0 | free scratch 303.7G/45093103i tmp 29.7G/1015651i workspace 303.7G/45093103i | repeat-01 collected 26/26 workers (60615 items) tests 15497 done 3 failed | 26 in flight, oldest 87s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................... [718%]
........................................................................ [721%]
.....................[contention-diag] +2412s soak 35p/256t rss 11.9G pss 10.7G swap 1.6G majflt 105932 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.7G pss 10.6G, 7 descendant rss 0.1G pss 0.0G | host avail 23.3G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.82 cpu 10.13 | cgroup 11.9G/max oom_kill 0 | free scratch 303.4G/45090647i tmp 29.7G/1015651i workspace 303.4G/45090647i | repeat-01 collected 26/26 workers (60615 items) tests 15633 done 3 failed | 25 in flight, oldest 103s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................... [724%]
........................................................................ [728%]
........................................................................ [731%]
........[contention-diag] +2428s soak 33p/244t rss 12.0G pss 10.8G swap 1.6G majflt 106308 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.7G pss 10.6G, 5 descendant rss 0.1G pss 0.1G | host avail 23.7G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.54 cpu 12.39 | cgroup 11.9G/max oom_kill 0 | free scratch 303.3G/45089888i tmp 29.7G/1015651i workspace 303.3G/45089888i | repeat-01 collected 26/26 workers (60615 items) tests 15847 done 3 failed | 26 in flight, oldest 118s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................................ [734%]
.............[contention-diag] +2443s soak 36p/279t rss 12.0G pss 10.8G swap 1.5G majflt 107183 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.8G pss 10.7G, 8 descendant rss 0.1G pss 0.1G | host avail 18.8G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.13 cpu 11.51 | cgroup 12.0G/max oom_kill 0 | free scratch 303.0G/45088646i tmp 29.7G/1015651i workspace 303.0G/45088646i | repeat-01 collected 26/26 workers (60615 items) tests 15922 done 3 failed | 25 in flight, oldest 134s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................................................... [738%]
........................................................................ [741%]
........[contention-diag] +2459s soak 32p/272t rss 12.0G pss 10.8G swap 1.5G majflt 107104 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.8G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 19.6G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.03 cpu 9.38 | cgroup 12.0G/max oom_kill 0 | free scratch 302.8G/45087175i tmp 29.7G/1015651i workspace 302.8G/45087175i | scratch used 0.3G in 57441 entries | repeat-01 collected 26/26 workers (60615 items) tests 16045 done 3 failed | 26 in flight, oldest 149s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
................................................................ [744%]
........................................................................ [748%]
........................................................................ [751%]
....................[contention-diag] +2475s soak 37p/240t rss 12.2G pss 11.0G swap 1.5G majflt 111694 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.8G pss 10.7G, 9 descendant rss 0.2G pss 0.2G | host avail 17.8G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.41 cpu 11.24 | cgroup 12.2G/max oom_kill 0 | free scratch 302.3G/45086458i tmp 29.7G/1015651i workspace 302.3G/45086458i | repeat-01 collected 26/26 workers (60615 items) tests 16284 done 3 failed | 26 in flight, oldest 165s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
.................................................... [754%]
........................................................................ [758%]
........................................................................ [761%]
........................................................................ [764%]
................................[contention-diag] +2490s soak 34p/240t rss 12.1G pss 10.9G swap 1.4G majflt 116394 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 6 descendant rss 0.1G pss 0.1G | host avail 20.0G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 2.97 cpu 12.38 | cgroup 12.1G/max oom_kill 0 | free scratch 300.9G/45085515i tmp 29.7G/1015651i workspace 300.9G/45085515i | repeat-01 collected 26/26 workers (60615 items) tests 16581 done 3 failed | 25 in flight, oldest 181s gw3 tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
........................................ [768%]
........................................................................ [771%]
........................................................................ [774%]
........................................................................ [778%]
...................................................................[contention-diag] +2506s soak 32p/239t rss 12.2G pss 11.0G swap 1.5G majflt 116723 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 18.3G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.44/0.44 io 2.86 cpu 11.37 | cgroup 12.2G/max oom_kill 0 | free scratch 300.6G/45086723i tmp 29.7G/1015651i workspace 300.6G/45086723i | repeat-01 collected 26/26 workers (60615 items) tests 16914 done 3 failed | 26 in flight, oldest 121s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
..... [781%]
........................................................................ [784%]
........................................................................ [788%]
.......................................................................[contention-diag] +2521s soak 32p/272t rss 11.9G pss 10.7G swap 1.6G majflt 117290 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.6G, 4 descendant rss 0.0G pss 0.0G | host avail 17.4G/62.7G swapfree 50.2G/64.0G oom_kill +0 | psi10 mem 0.97/0.22 io 3.34 cpu 10.45 | cgroup 11.8G/max oom_kill 0 | free scratch 300.4G/45085732i tmp 29.7G/1015651i workspace 300.4G/45085732i | repeat-01 collected 26/26 workers (60615 items) tests 17132 done 3 failed | 26 in flight, oldest 136s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_matches_live_production_source
. [791%]
........................................................................ [794%]
........................................................................ [798%]
...........[contention-diag] +2536s soak 33p/289t rss 11.8G pss 10.6G swap 1.8G majflt 118209 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.5G, 5 descendant rss 0.0G pss 0.0G | host avail 16.0G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.71/0.29 io 2.88 cpu 10.7 | cgroup 11.7G/max oom_kill 0 | free scratch 300.2G/45085343i tmp 29.7G/1015651i workspace 300.2G/45085343i | repeat-01 collected 26/26 workers (60615 items) tests 17290 done 3 failed | 26 in flight, oldest 109s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
............................................................. [801%]
........................................................................ [804%]
.................[contention-diag] +2552s soak 31p/278t rss 11.9G pss 10.7G swap 1.7G majflt 118652 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.5G, 3 descendant rss 0.1G pss 0.0G | host avail 20.0G/62.7G swapfree 50.1G/64.0G oom_kill +0 | psi10 mem 0.14/0.05 io 1.53 cpu 8.52 | cgroup 11.8G/max oom_kill 0 | free scratch 299.4G/45082656i tmp 29.7G/1015651i workspace 299.4G/45082656i | repeat-01 collected 26/26 workers (60615 items) tests 17426 done 3 failed | 26 in flight, oldest 125s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
........F[contention-failure] call tests/completion/test_zsh_smoke.py::test_tab_completes_after_root_print_command_option[sase bead sh-sase bead show ]: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw5/test_tab_completes_after_root_0')
typed = 'sase bead sh', expected = 'sase bead show '

    @pytest.mark.parametrize(
        ("typed", "expected"),
        [
            ("sase bead sh", "sase bead show "),
            ("sase -p bead sh", "sase -p bead show "),
            ("sase --print-command bead sh", "sase --print-command bead show "),
        ],
    )
    def test_tab_completes_after_root_print_command_option(
        tmp_path: Path, typed: str, expected: str
    ) -> None:
        fpath_dir = tmp_path / "fpath"
        fpath_dir.mkdir()
        _write_live_script(fpath_dir)
    
>       captured = _pty_capture_completion(tmp_path, fpath_dir, typed)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/completion/test_zsh_smoke.py:230: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/completion/test_zsh_smoke.py:602: in _pty_capture_completion
    screen = _read_until(fd, marker.encode(), timeout=5.0)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

fd = 14, needle = b'__SASE_CAPTURE_105413799907997__', timeout = 5.0

    def _read_until(fd: int, needle: bytes, timeout: float = 5.0) -> bytes:
        buf = b""
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            remaining = deadline - time.monotonic()
            ready, _, _ = select.select([fd], [], [], max(0.0, remaining))
            if not ready:
                continue
            try:
                chunk = os.read(fd, 4096)
            except OSError:
                break
            if not chunk:
                break
            buf += chunk
            if needle in buf:
                return buf
>       raise TimeoutError(f"timed out waiting for {needle!r}; got {buf!r}")
E       TimeoutError: timed out waiting for b'__SASE_CAPTURE_105413799907997__'; got b'sase bead sh'

tests/completion/test_zsh_smoke.py:669: TimeoutError
.............................................. [808%]
..................................[contention-diag] +2567s soak 35p/273t rss 12.0G pss 10.7G swap 1.8G majflt 119145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 7 descendant rss 0.2G pss 0.1G | host avail 14.8G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 1.23/0.74 io 1.82 cpu 9.87 | cgroup 12.0G/max oom_kill 0 | free scratch 299.7G/45088924i tmp 29.7G/1015651i workspace 299.7G/45088924i | repeat-01 collected 26/26 workers (60615 items) tests 17521 done 4 failed | 25 in flight, oldest 140s gw13 tests/ace/tui/test_epic_panel_arrival_frames.py::test_scenario_starts_with_the_selection_below_the_epic_fold
...................................... [811%]
........................................................................ [814%]
........................................................................ [818%]
........................................................................ [821%]
..........[contention-diag] +2583s soak 30p/227t rss 11.8G pss 10.6G swap 1.8G majflt 119979 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 2 descendant rss 0.0G pss 0.0G | host avail 17.7G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.24/0.14 io 2.83 cpu 11.07 | cgroup 11.8G/max oom_kill 0 | free scratch 299.5G/45085304i tmp 29.7G/1015651i workspace 299.5G/45085304i | scratch used 0.3G in 59914 entries | repeat-01 collected 26/26 workers (60615 items) tests 17773 done 4 failed | 26 in flight, oldest 54s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_manual_update_drops_expired_load_freshness
.............................................................. [824%]
........................................................................ [828%]
.................[contention-diag] +2600s soak 33p/251t rss 11.8G pss 10.6G swap 1.8G majflt 120357 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.5G, 5 descendant rss 0.0G pss 0.0G | host avail 17.3G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.04/0.02 io 2.47 cpu 11.99 | cgroup 11.8G/max oom_kill 0 | free scratch 299.2G/45084498i tmp 29.7G/1015650i workspace 299.2G/45084498i | repeat-01 collected 26/26 workers (60615 items) tests 17942 done 4 failed | 26 in flight, oldest 70s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
....................................................... [831%]
...........................................[contention-diag] +2615s soak 34p/269t rss 11.8G pss 10.6G swap 1.8G majflt 120477 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.5G, 6 descendant rss 0.0G pss 0.0G | host avail 18.3G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.88 cpu 12.16 | cgroup 11.8G/max oom_kill 0 | free scratch 298.9G/45084115i tmp 29.7G/1015650i workspace 298.9G/45084115i | repeat-01 collected 26/26 workers (60615 items) tests 18042 done 4 failed | 26 in flight, oldest 86s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................. [834%]
........................................................................ [838%]
........................................................................ [841%]
.........[contention-diag] +2630s soak 30p/240t rss 11.8G pss 10.6G swap 1.8G majflt 120661 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 2 descendant rss 0.0G pss 0.0G | host avail 15.7G/62.7G swapfree 49.9G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 2.36 cpu 12.29 | cgroup 11.7G/max oom_kill 0 | free scratch 298.9G/45083734i tmp 29.7G/1015650i workspace 298.9G/45083734i | repeat-01 collected 26/26 workers (60615 items) tests 18212 done 4 failed | 26 in flight, oldest 101s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................................................... [844%]
..................................................[contention-diag] +2646s soak 34p/253t rss 11.9G pss 10.6G swap 1.9G majflt 120829 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.6G pss 10.4G, 6 descendant rss 0.1G pss 0.1G | host avail 11.9G/62.7G swapfree 49.7G/64.0G oom_kill +0 | psi10 mem 0.76/0.48 io 4.34 cpu 9.89 | cgroup 11.1G/max oom_kill 0 | free scratch 298.6G/45083319i tmp 29.7G/1015649i workspace 298.6G/45083319i | repeat-01 collected 26/26 workers (60615 items) tests 18330 done 4 failed | 26 in flight, oldest 117s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
...................... [848%]
........................................................................ [851%]
.........................................[contention-diag] +2662s soak 29p/240t rss 11.7G pss 10.5G swap 1.9G majflt 121340 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.5G pss 10.3G, 1 descendant rss 0.0G pss 0.0G | host avail 14.7G/62.7G swapfree 49.4G/64.0G oom_kill +0 | psi10 mem 0.68/0.25 io 6.15 cpu 9.4 | cgroup 11.1G/max oom_kill 0 | free scratch 297.0G/45079242i tmp 29.7G/1015650i workspace 297.0G/45079242i | repeat-01 collected 26/26 workers (60615 items) tests 18462 done 4 failed | 25 in flight, oldest 132s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_inventory_rejects_legacy_callable_submitters
............................... [854%]
........................................................................ [858%]
........................................................................ [861%]
................[contention-diag] +2677s soak 31p/238t rss 11.6G pss 10.3G swap 2.1G majflt 121751 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.4G pss 10.2G, 3 descendant rss 0.0G pss 0.0G | host avail 13.9G/62.7G swapfree 49.1G/64.0G oom_kill +0 | psi10 mem 5.0/3.75 io 16.13 cpu 8.13 | cgroup 10.9G/max oom_kill 0 | free scratch 295.3G/45075630i tmp 29.7G/1015650i workspace 295.3G/45075630i | repeat-01 collected 26/26 workers (60615 items) tests 18648 done 4 failed | 26 in flight, oldest 37s gw7 tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_offline_reload_does_not_retain_freshness
........................................................ [864%]
........................................................................ [867%]
........................................................................ [871%]
........................................................................ [874%]
........................................................[contention-diag] +2693s soak 31p/218t rss 11.5G pss 10.3G swap 2.2G majflt 122313 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.3G pss 10.2G, 3 descendant rss 0.0G pss 0.0G | host avail 16.0G/62.7G swapfree 49.0G/64.0G oom_kill +0 | psi10 mem 3.77/2.62 io 13.96 cpu 8.94 | cgroup 10.9G/max oom_kill 0 | free scratch 293.6G/45074712i tmp 29.7G/1015650i workspace 293.6G/45074712i | repeat-01 collected 26/26 workers (60615 items) tests 18976 done 4 failed | 26 in flight, oldest 43s gw19 tests/ace/tui/test_statistics_view_number_select.py::test_range_input_keeps_prefix_digit_as_text
................ [877%]
........................................................................ [881%]
..........................[contention-diag] +2708s soak 35p/237t rss 11.5G pss 10.2G swap 2.3G majflt 124137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.1G, 7 descendant rss 0.0G pss 0.0G | host avail 14.9G/62.7G swapfree 48.8G/64.0G oom_kill +0 | psi10 mem 3.17/2.08 io 8.15 cpu 8.43 | cgroup 10.8G/max oom_kill 0 | free scratch 292.6G/45072865i tmp 29.7G/1015650i workspace 292.6G/45072865i | scratch used 0.1G in 9656 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 19093 done 4 failed | 26 in flight, oldest 49s gw24 tests/ace/tui/test_statistics_pane_interactions.py::test_macro_focus_picker_all_clear_key_and_cancel
.............................................. [884%]
........................................................................ [887%]
........................s............................................... [891%]
............[contention-diag] +2726s soak 31p/244t rss 11.5G pss 10.3G swap 2.3G majflt 125917 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.3G pss 10.1G, 3 descendant rss 0.0G pss 0.0G | host avail 21.3G/62.7G swapfree 48.9G/64.0G oom_kill +0 | psi10 mem 0.82/0.34 io 4.56 cpu 11.94 | cgroup 10.9G/max oom_kill 0 | free scratch 291.8G/45066652i tmp 29.7G/1015649i workspace 291.8G/45066652i | repeat-01 collected 26/26 workers (60615 items) tests 19300 done 4 failed | 26 in flight, oldest 56s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
............................................................ [894%]
.....F[contention-failure] call tests/completion/test_zsh_smoke.py::test_dynamic_completion_does_not_leak_extendedglob_to_shell: tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw5/test_dynamic_completion_does_n0')

    def test_dynamic_completion_does_not_leak_extendedglob_to_shell(
        tmp_path: Path,
    ) -> None:
        fpath_dir = tmp_path / "fpath"
        fpath_dir.mkdir()
        _write_live_script(fpath_dir)
        bin_dir, _calls = _write_logged_fixture_sase(
            tmp_path,
            "zzz-completion-fixture\tFixture bead",
        )
    
>       captured = _pty_capture_completion(
            tmp_path,
            fpath_dir,
            "sase bead show zzz",
            bin_dir=bin_dir,
        )

tests/completion/test_zsh_smoke.py:446: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/completion/test_zsh_smoke.py:602: in _pty_capture_completion
    screen = _read_until(fd, marker.encode(), timeout=5.0)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

fd = 14, needle = b'__SASE_CAPTURE_105597422721071__', timeout = 5.0

    def _read_until(fd: int, needle: bytes, timeout: float = 5.0) -> bytes:
        buf = b""
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            remaining = deadline - time.monotonic()
            ready, _, _ = select.select([fd], [], [], max(0.0, remaining))
            if not ready:
                continue
            try:
                chunk = os.read(fd, 4096)
            except OSError:
                break
            if not chunk:
                break
            buf += chunk
            if needle in buf:
                return buf
>       raise TimeoutError(f"timed out waiting for {needle!r}; got {buf!r}")
E       TimeoutError: timed out waiting for b'__SASE_CAPTURE_105597422721071__'; got b'sase bead show zzz'

tests/completion/test_zsh_smoke.py:669: TimeoutError
........................s...s..................................... [897%]
........................................................................ [901%]
........................................................................ [904%]
..[contention-diag] +2741s soak 30p/246t rss 11.5G pss 10.3G swap 2.2G majflt 127708 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 10.2G, 2 descendant rss 0.0G pss 0.0G | host avail 27.6G/62.7G swapfree 49.0G/64.0G oom_kill +0 | psi10 mem 0.34/0.06 io 2.89 cpu 11.83 | cgroup 10.9G/max oom_kill 0 | free scratch 291.9G/45069839i tmp 29.7G/1015650i workspace 291.9G/45069839i | repeat-01 collected 26/26 workers (60615 items) tests 19575 done 5 failed | 26 in flight, oldest 72s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
...................................................................... [907%]
........................................................................ [911%]
....................................................[contention-diag] +2757s soak 32p/241t rss 11.6G pss 10.3G swap 2.2G majflt 131318 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.4G pss 10.2G, 4 descendant rss 0.0G pss 0.0G | host avail 25.6G/62.7G swapfree 49.0G/64.0G oom_kill +0 | psi10 mem 0.11/0.01 io 4.52 cpu 23.73 | cgroup 11.0G/max oom_kill 0 | free scratch 291.8G/45038378i tmp 29.7G/1015588i workspace 291.8G/45038378i | repeat-01 collected 26/26 workers (60615 items) tests 19768 done 5 failed | 26 in flight, oldest 87s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.................... [914%]
........................................................................ [917%]
...........................................................[contention-diag] +2772s soak 30p/248t rss 11.6G pss 10.4G swap 2.1G majflt 139572 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.5G pss 10.3G, 2 descendant rss 0.0G pss 0.0G | host avail 24.7G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.12/0.0 io 15.11 cpu 14.77 | cgroup 11.1G/max oom_kill 0 | free scratch 291.3G/45013433i tmp 29.6G/1014875i workspace 291.3G/45013433i | repeat-01 collected 26/26 workers (60615 items) tests 19920 done 5 failed | 24 in flight, oldest 103s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
............. [921%]
........................................................................ [924%]
............................................[contention-diag] +2788s soak 30p/261t rss 11.7G pss 10.5G swap 2.1G majflt 147077 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.5G pss 10.3G, 2 descendant rss 0.0G pss 0.0G | host avail 22.6G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 32.49 cpu 9.2 | cgroup 11.1G/max oom_kill 0 | free scratch 291.3G/45014661i tmp 29.7G/1015164i workspace 291.3G/45014661i | repeat-01 collected 26/26 workers (60615 items) tests 20049 done 5 failed | 25 in flight, oldest 119s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
............................ [927%]
........................................................................ [931%]
....................................[contention-diag] +2804s soak 33p/275t rss 11.8G pss 10.5G swap 2.1G majflt 150340 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.4G, 5 descendant rss 0.1G pss 0.0G | host avail 30.0G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 26.2 cpu 8.76 | cgroup 11.2G/max oom_kill 0 | free scratch 293.8G/45013949i tmp 29.7G/1015544i workspace 293.8G/45013949i | repeat-01 collected 26/26 workers (60615 items) tests 20192 done 5 failed | 26 in flight, oldest 135s gw6 tests/ace/tui/test_proc_producer_inventory.py::test_producer_calls_match_submit_signatures
.................................... [934%]
........................................................................ [937%]
........................................................................ [941%]
..................................................................[contention-diag] +2820s soak 39p/292t rss 11.9G pss 10.6G swap 2.0G majflt 151982 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.4G, 11 descendant rss 0.1G pss 0.1G | host avail 28.9G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 1.07/0.0 io 7.69 cpu 16.9 | cgroup 11.3G/max oom_kill 0 | free scratch 293.8G/45013230i tmp 29.7G/1015543i workspace 293.8G/45013230i | repeat-01 collected 26/26 workers (60615 items) tests 20427 done 5 failed | 26 in flight, oldest 73s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_auto_refresh_soak_keeps_event_loop_and_message_pump_responsive
...... [944%]
........................................................................ [947%]
........................................................................ [951%]
........................................................................ [954%]
.............[contention-diag] +2835s soak 33p/267t rss 11.9G pss 10.6G swap 2.0G majflt 153216 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.4G, 5 descendant rss 0.1G pss 0.1G | host avail 30.4G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.98/0.25 io 3.24 cpu 19.26 | cgroup 11.3G/max oom_kill 0 | free scratch 293.8G/45012836i tmp 29.7G/1015570i workspace 293.8G/45012836i | scratch used 0.2G in 30326 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 20644 done 5 failed | 26 in flight, oldest 44s gw9 tests/ace/tui/test_projects_pane.py::test_projects_filter_applies_once_per_keystroke
........................................................... [957%]
........................................................................ [961%]
..........[contention-diag] +2852s soak 35p/264t rss 12.0G pss 10.7G swap 2.1G majflt 154074 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.4G, 7 descendant rss 0.2G pss 0.2G | host avail 27.2G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.26/0.05 io 2.44 cpu 14.8 | cgroup 11.5G/max oom_kill 0 | free scratch 293.8G/45012366i tmp 29.7G/1015598i workspace 293.8G/45012366i | repeat-01 collected 26/26 workers (60615 items) tests 20815 done 5 failed | 26 in flight, oldest 31s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_overview_revalidation_tick_never_paints_loading
.............................................................. [964%]
........................................................................ [967%]
..................................[contention-diag] +2868s soak 36p/280t rss 12.0G pss 10.7G swap 2.0G majflt 154383 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.1G pss 0.1G, 26 worker rss 11.6G pss 10.4G, 8 descendant rss 0.2G pss 0.2G | host avail 27.5G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 3.71 cpu 11.91 | cgroup 11.5G/max oom_kill 0 | free scratch 293.8G/45011996i tmp 29.7G/1015598i workspace 293.8G/45011996i | repeat-01 collected 26/26 workers (60615 items) tests 20976 done 5 failed | 26 in flight, oldest 47s gw11 tests/ace/tui/test_statistics_pane_loading.py::test_overview_revalidation_tick_never_paints_loading
...................................... [971%]
........................................................................ [974%]
............................................[contention-diag] +2883s soak 40p/270t rss 12.2G pss 10.8G swap 2.1G majflt 155584 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.4G, 12 descendant rss 0.4G pss 0.3G | host avail 27.9G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.0 io 1.73 cpu 12.22 | cgroup 11.7G/max oom_kill 0 | free scratch 293.8G/45010503i tmp 29.7G/1015598i workspace 293.8G/45010503i | repeat-01 collected 26/26 workers (60615 items) tests 21135 done 5 failed | 26 in flight, oldest 61s gw7 tests/ace/tui/test_popup_panel_tab_switch_keymaps.py::test_help_guide_tab_uses_configured_tab_switch_keys
............................ [977%]
........................................................................ [981%]
........................................................................ [984%]
........................................................................ [987%]
.................................................................[contention-diag] +2898s soak 37p/221t rss 12.1G pss 10.8G swap 2.0G majflt 157137 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.6G pss 10.4G, 9 descendant rss 0.3G pss 0.2G | host avail 25.8G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 1.05/0.0 io 2.72 cpu 12.55 | cgroup 11.6G/max oom_kill 0 | free scratch 293.8G/45010711i tmp 29.7G/1015598i workspace 293.8G/45010711i | repeat-01 collected 26/26 workers (60615 items) tests 21445 done 5 failed | 26 in flight, oldest 58s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
....... [991%]
........................................................................ [994%]
........................................................................ [997%]
..................................................[contention-diag] +2914s soak 36p/199t rss 12.2G pss 10.8G swap 2.0G majflt 158123 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.4G, 8 descendant rss 0.3G pss 0.3G | host avail 25.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.31/0.09 io 2.38 cpu 12.18 | cgroup 11.7G/max oom_kill 0 | free scratch 293.8G/45011335i tmp 29.7G/1015598i workspace 293.8G/45011335i | repeat-01 collected 26/26 workers (60615 items) tests 21642 done 5 failed | 26 in flight, oldest 73s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
...................... [1001%]
....................s................................................... [1004%]
........................................................................ [1007%]
.............................[contention-diag] +2929s soak 38p/210t rss 12.3G pss 10.9G swap 2.1G majflt 159082 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.5G, 10 descendant rss 0.4G pss 0.3G | host avail 23.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.27/0.01 io 2.15 cpu 14.34 | cgroup 11.8G/max oom_kill 0 | free scratch 293.8G/45009433i tmp 29.7G/1015598i workspace 293.8G/45009433i | repeat-01 collected 26/26 workers (60615 items) tests 21839 done 5 failed | 26 in flight, oldest 89s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
........................................... [1010%]
........................................................................ [1014%]
........................................................................ [1017%]
........................................................................ [1020%]
........................................................................ [1024%]
.........................................s.....[contention-diag] +2945s soak 36p/224t rss 12.1G pss 10.7G swap 2.0G majflt 160350 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.1G, 26 worker rss 11.7G pss 10.5G, 8 descendant rss 0.2G pss 0.1G | host avail 24.3G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.1/0.0 io 1.89 cpu 15.02 | cgroup 11.6G/max oom_kill 0 | free scratch 293.8G/45007288i tmp 29.7G/1015598i workspace 293.8G/45007287i | repeat-01 collected 26/26 workers (60615 items) tests 22193 done 5 failed | 26 in flight, oldest 105s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
......................... [1027%]
........................................................................ [1030%]
........................................................................ [1034%]
........................................................................ [1037%]
........................................................................ [1040%]
........................................................................ [1044%]
..[contention-diag] +2960s soak 39p/208t rss 12.3G pss 10.8G swap 1.9G majflt 167070 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.5G, 11 descendant rss 0.3G pss 0.2G | host avail 26.3G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 2.27/0.0 io 1.41 cpu 18.18 | cgroup 11.7G/max oom_kill 0 | free scratch 293.4G/45003259i tmp 29.7G/1015598i workspace 293.4G/45003259i | scratch used 0.3G in 52981 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 22565 done 5 failed | 25 in flight, oldest 120s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
...................................................................... [1047%]
.....................................[contention-diag] +2977s soak 36p/197t rss 12.3G pss 10.9G swap 2.0G majflt 167564 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.5G, 8 descendant rss 0.3G pss 0.2G | host avail 24.5G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 1.71/0.0 io 1.98 cpu 18.84 | cgroup 12.0G/max oom_kill 0 | free scratch 292.9G/44987813i tmp 29.7G/1015597i workspace 292.9G/44987813i | repeat-01 collected 26/26 workers (60615 items) tests 22702 done 5 failed | 25 in flight, oldest 137s gw1 tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
................................... [1050%]
........................................................................ [1054%]
........................................................................ [1057%]
........................................................................ [1060%]
........................................................................ [1064%]
................................[contention-diag] +2993s soak 37p/194t rss 12.1G pss 10.8G swap 1.9G majflt 168170 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.5G, 9 descendant rss 0.1G pss 0.1G | host avail 24.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.42/0.0 io 2.28 cpu 15.05 | cgroup 11.7G/max oom_kill 0 | free scratch 292.6G/44986765i tmp 29.7G/1015597i workspace 292.6G/44986765i | repeat-01 collected 26/26 workers (60615 items) tests 23055 done 5 failed | 25 in flight, oldest 47s gw19 tests/ace/tui/test_statistics_view_number_select.py::test_configured_prefix_arms_the_same_number_selection
........................................ [1067%]
........................................................................ [1070%]
........................................................................ [1074%]
........................................................................ [1077%]
........................................................................ [1080%]
........................................................................ [1084%]
........................................................................ [1087%]
........................................................................ [1090%]
........................................................[contention-diag] +3008s soak 34p/172t rss 12.1G pss 10.8G swap 1.9G majflt 168937 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.5G, 6 descendant rss 0.2G pss 0.1G | host avail 25.7G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.31/0.0 io 4.42 cpu 19.18 | cgroup 11.7G/max oom_kill 0 | free scratch 292.3G/44985209i tmp 29.7G/1015597i workspace 292.3G/44985209i | repeat-01 collected 26/26 workers (60615 items) tests 23657 done 5 failed | 26 in flight, oldest 44s gw22 tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace
................ [1094%]
........................................................................ [1097%]
........................................................................ [1100%]
........................................................................ [1104%]
........................................................................ [1107%]
........................................................................ [1110%]
........................................................................ [1114%]
........................................................................ [1117%]
................................................[contention-diag] +3024s soak 34p/181t rss 12.1G pss 10.7G swap 1.9G majflt 170096 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.5G, 6 descendant rss 0.1G pss 0.1G | host avail 24.2G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.6/0.0 io 2.98 cpu 16.5 | cgroup 11.4G/max oom_kill 0 | free scratch 292.0G/44984083i tmp 29.7G/1015596i workspace 292.0G/44984083i | repeat-01 collected 26/26 workers (60615 items) tests 24214 done 5 failed | 26 in flight, oldest 59s gw22 tests/fakey/test_pipe_e2e.py::test_default_pipe_creates_agent_session_member_with_fork_and_shared_workspace
........................ [1120%]
........................................................................ [1124%]
........................................................................ [1127%]
........................................................................ [1130%]
........................................................................ [1134%]
........................................................................ [1137%]
................[contention-diag] +3039s soak 35p/174t rss 12.2G pss 10.9G swap 1.9G majflt 171586 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.5G, 7 descendant rss 0.3G pss 0.2G | host avail 24.7G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 2.05/1.1 io 7.38 cpu 14.97 | cgroup 11.5G/max oom_kill 0 | free scratch 291.1G/44975825i tmp 29.7G/1015596i workspace 291.1G/44975825i | repeat-01 collected 26/26 workers (60615 items) tests 24637 done 5 failed | 25 in flight, oldest 65s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
........................................................ [1140%]
........................................................................ [1144%]
......................................................................[contention-diag] +3054s soak 36p/182t rss 12.2G pss 10.8G swap 1.9G majflt 171302 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.7G pss 10.5G, 8 descendant rss 0.2G pss 0.2G | host avail 25.0G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.5/0.27 io 8.97 cpu 13.32 | cgroup 11.6G/max oom_kill 0 | free scratch 289.5G/44971030i tmp 29.7G/1015596i workspace 289.5G/44971030i | repeat-01 collected 26/26 workers (60615 items) tests 24826 done 5 failed | 26 in flight, oldest 80s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.. [1147%]
........................................................................ [1150%]
........................................................................ [1153%]
..............................................................[contention-diag] +3070s soak 38p/187t rss 12.1G pss 10.8G swap 1.9G majflt 172329 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.5G, 10 descendant rss 0.1G pss 0.1G | host avail 23.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.28/0.23 io 3.15 cpu 14.31 | cgroup 11.5G/max oom_kill 0 | free scratch 289.3G/44970061i tmp 29.7G/1015596i workspace 289.3G/44970061i | repeat-01 collected 26/26 workers (60615 items) tests 25046 done 5 failed | 26 in flight, oldest 96s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.......... [1157%]
........................................................................ [1160%]
........................................................................ [1163%]
.....................................................................[contention-diag] +3085s soak 31p/179t rss 12.1G pss 10.8G swap 1.9G majflt 172685 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.5G, 3 descendant rss 0.0G pss 0.0G | host avail 21.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.67/0.44 io 3.4 cpu 14.84 | cgroup 11.6G/max oom_kill 0 | free scratch 289.1G/44969279i tmp 29.7G/1015596i workspace 289.1G/44969279i | scratch used 0.1G in 25047 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 25216 done 5 failed | 26 in flight, oldest 111s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
... [1167%]
........................................................................ [1170%]
........................................................................ [1173%]
........................................................................ [1177%]
........................................................................ [1180%]
..............[contention-diag] +3103s soak 31p/175t rss 12.1G pss 10.8G swap 1.9G majflt 173075 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.5G, 3 descendant rss 0.0G pss 0.0G | host avail 20.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.17/0.08 io 2.65 cpu 16.39 | cgroup 11.7G/max oom_kill 0 | free scratch 289.0G/44968170i tmp 29.7G/1015596i workspace 289.0G/44968170i | repeat-01 collected 26/26 workers (60615 items) tests 25569 done 5 failed | 26 in flight, oldest 128s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
.......................................................... [1183%]
....s................................................................... [1187%]
........................................................................ [1190%]
........................................................................ [1193%]
[contention-diag] +3118s soak 32p/172t rss 12.1G pss 10.8G swap 1.9G majflt 173829 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.6G, 4 descendant rss 0.0G pss 0.0G | host avail 19.0G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.01 io 1.63 cpu 13.55 | cgroup 11.7G/max oom_kill 0 | free scratch 293.2G/45020811i tmp 29.7G/1015596i workspace 293.2G/45020811i | repeat-01 collected 26/26 workers (60615 items) tests 25841 done 5 failed | 26 in flight, oldest 144s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
........................................................................ [1197%]
....................................................................[contention-diag] +3133s soak 38p/181t rss 12.1G pss 10.8G swap 1.9G majflt 174224 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.6G, 10 descendant rss 0.1G pss 0.0G | host avail 19.1G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.47 cpu 15.54 | cgroup 11.7G/max oom_kill 0 | free scratch 293.4G/45022529i tmp 29.7G/1015596i workspace 293.4G/45022529i | repeat-01 collected 26/26 workers (60615 items) tests 25979 done 5 failed | 26 in flight, oldest 159s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
.... [1200%]
........................................................................ [1203%]
........................................................................ [1207%]
........................................................................ [1210%]
........................................................................ [1213%]
........................................................................ [1217%]
.....................[contention-diag] +3149s soak 32p/172t rss 12.1G pss 10.8G swap 1.8G majflt 174754 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.6G, 4 descendant rss 0.0G pss 0.0G | host avail 21.0G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.21/0.21 io 0.99 cpu 17.69 | cgroup 11.7G/max oom_kill 0 | free scratch 293.3G/45021737i tmp 29.7G/1015596i workspace 293.3G/45021737i | repeat-01 collected 26/26 workers (60615 items) tests 26339 done 5 failed | 26 in flight, oldest 175s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
................................................... [1220%]
........................................................................ [1223%]
........................................................................ [1227%]
........................................................................ [1230%]
........................................................................ [1233%]
................................................................[contention-diag] +3164s soak 35p/175t rss 12.2G pss 10.9G swap 1.8G majflt 175119 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.8G pss 10.6G, 7 descendant rss 0.1G pss 0.1G | host avail 22.5G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 1.76 cpu 21.18 | cgroup 11.7G/max oom_kill 0 | free scratch 293.3G/45020270i tmp 29.7G/1015596i workspace 293.3G/45020270i | repeat-01 collected 26/26 workers (60615 items) tests 26770 done 5 failed | 26 in flight, oldest 190s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
........ [1237%]
........................................................................ [1240%]
........................................................................ [1243%]
........................................................................ [1247%]
........................................................................ [1250%]
........................................................................ [1253%]
................[contention-diag] +3180s soak 37p/174t rss 12.3G pss 10.7G swap 1.8G majflt 176192 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.4G, 9 descendant rss 0.1G pss 0.1G | host avail 23.8G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.36 cpu 20.34 | cgroup 11.9G/max oom_kill 0 | free scratch 293.3G/45018932i tmp 29.7G/1015596i workspace 293.3G/45018932i | repeat-01 collected 26/26 workers (60615 items) tests 27155 done 5 failed | 26 in flight, oldest 205s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
........................................................ [1257%]
........................................................................ [1260%]
........................................................................ [1263%]
...............[contention-diag] +3195s soak 34p/170t rss 12.3G pss 10.9G swap 1.8G majflt 176545 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.6G, 6 descendant rss 0.2G pss 0.1G | host avail 27.2G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.5 cpu 20.38 | cgroup 11.9G/max oom_kill 0 | free scratch 293.3G/45018562i tmp 29.7G/1015596i workspace 293.3G/45018562i | repeat-01 collected 26/26 workers (60615 items) tests 27368 done 5 failed | 25 in flight, oldest 221s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
......................................................... [1267%]
........................................................................ [1270%]
........................................................[contention-diag] +3210s soak 35p/167t rss 12.3G pss 11.0G swap 1.8G majflt 177071 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.6G, 7 descendant rss 0.2G pss 0.1G | host avail 27.8G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.3 cpu 21.17 | cgroup 12.0G/max oom_kill 0 | free scratch 293.3G/45018669i tmp 29.7G/1015596i workspace 293.3G/45018669i | scratch used 0.4G in 66390 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 27552 done 5 failed | 25 in flight, oldest 236s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
................ [1273%]
........................................................................ [1277%]
........[contention-diag] +3228s soak 37p/177t rss 12.4G pss 11.0G swap 1.8G majflt 177534 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 11.9G pss 10.6G, 9 descendant rss 0.2G pss 0.2G | host avail 27.0G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.09 cpu 22.57 | cgroup 12.2G/max oom_kill 0 | free scratch 293.3G/45018240i tmp 29.7G/1015596i workspace 293.3G/45018240i | repeat-01 collected 26/26 workers (60615 items) tests 27654 done 5 failed | 25 in flight, oldest 253s gw23 tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope | 1 hazardous kill call(s)
................................................................ [1280%]
........................................................................ [1283%]
........[contention-diag] +3243s soak 35p/173t rss 12.5G pss 11.1G swap 1.8G majflt 178574 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 7 descendant rss 0.3G pss 0.2G | host avail 26.7G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.36 cpu 18.27 | cgroup 12.2G/max oom_kill 0 | free scratch 293.3G/45017894i tmp 29.7G/1015596i workspace 293.3G/45017894i | repeat-01 collected 26/26 workers (60615 items) tests 27777 done 5 failed | 22 in flight, oldest 220s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................................ [1287%]
........................................................................ [1290%]
........................................................................ [1293%]
................[contention-diag] +3258s soak 38p/173t rss 12.5G pss 11.1G swap 1.8G majflt 178813 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 10 descendant rss 0.3G pss 0.2G | host avail 26.1G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.75 cpu 18.27 | cgroup 12.1G/max oom_kill 0 | free scratch 293.3G/45017056i tmp 29.7G/1015596i workspace 293.3G/45017056i | repeat-01 collected 26/26 workers (60615 items) tests 28022 done 5 failed | 25 in flight, oldest 236s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................................................ [1296%]
........................................................................ [1300%]
........................................................................ [1303%]
........................................................................ [1306%]
..............................[contention-diag] +3274s soak 38p/180t rss 12.3G pss 11.0G swap 1.8G majflt 179145 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 10 descendant rss 0.1G pss 0.1G | host avail 22.4G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.2 cpu 16.11 | cgroup 12.1G/max oom_kill 0 | free scratch 293.6G/45015668i tmp 29.7G/1015596i workspace 293.6G/45015668i | repeat-01 collected 26/26 workers (60615 items) tests 28317 done 5 failed | 25 in flight, oldest 251s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.......................................... [1310%]
........................................................................ [1313%]
........................................................................ [1316%]
........................................................................ [1320%]
......................................................[contention-diag] +3289s soak 36p/180t rss 12.4G pss 11.0G swap 1.8G majflt 179647 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 8 descendant rss 0.2G pss 0.1G | host avail 21.5G/62.7G swapfree 51.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.69 cpu 13.28 | cgroup 12.1G/max oom_kill 0 | free scratch 292.7G/45013338i tmp 29.7G/1015596i workspace 292.7G/45013338i | repeat-01 collected 26/26 workers (60615 items) tests 28632 done 5 failed | 25 in flight, oldest 266s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
.................. [1323%]
........................................................................ [1326%]
........................................................................ [1330%]
........................................................................ [1333%]
........................................................................ [1336%]
........................................................................ [1340%]
.....................[contention-diag] +3304s soak 35p/171t rss 12.5G pss 11.0G swap 1.8G majflt 180060 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 7 descendant rss 0.2G pss 0.1G | host avail 21.4G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.69/0.36 io 1.94 cpu 13.93 | cgroup 12.1G/max oom_kill 0 | free scratch 292.6G/45012298i tmp 29.7G/1015596i workspace 292.6G/45012298i | repeat-01 collected 26/26 workers (60615 items) tests 29029 done 5 failed | 25 in flight, oldest 282s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
................................................... [1343%]
........................................................................ [1346%]
........................................................................ [1350%]
................................................[contention-diag] +3320s soak 35p/165t rss 12.4G pss 11.0G swap 1.8G majflt 180393 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 7 descendant rss 0.1G pss 0.1G | host avail 20.1G/62.7G swapfree 51.8G/64.0G oom_kill +0 | psi10 mem 0.13/0.07 io 2.2 cpu 18.22 | cgroup 12.0G/max oom_kill 0 | free scratch 292.4G/45011570i tmp 29.7G/1015596i workspace 292.4G/45011570i | repeat-01 collected 26/26 workers (60615 items) tests 29273 done 5 failed | 25 in flight, oldest 297s gw15 tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy | 1 hazardous kill call(s)
........................ [1353%]
........................................................................ [1356%]
........................................................................ [1360%]
........................................................................ [1363%]
........................................................................ [1366%]
..[contention-diag] +3335s soak 35p/171t rss 12.5G pss 11.1G swap 1.8G majflt 181095 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 7 descendant rss 0.2G pss 0.2G | host avail 19.4G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.84/0.01 io 1.84 cpu 18.17 | cgroup 12.1G/max oom_kill 0 | free scratch 292.1G/45010314i tmp 29.7G/1015596i workspace 292.1G/45010314i | scratch used 0.4G in 63811 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 29536 done 5 failed | 25 in flight, oldest 201s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
...................................................................... [1370%]
........................................................................ [1373%]
........................................................................ [1376%]
.................................[contention-diag] +3352s soak 32p/163t rss 12.4G pss 11.0G swap 1.8G majflt 181398 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 17.3G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.65/0.33 io 3.04 cpu 18.7 | cgroup 12.1G/max oom_kill 0 | free scratch 292.0G/45009266i tmp 29.7G/1015596i workspace 292.0G/45009266i | repeat-01 collected 26/26 workers (60615 items) tests 29828 done 5 failed | 25 in flight, oldest 218s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
....................................... [1380%]
........................................................................ [1383%]
........................................................................ [1386%]
........................................................................ [1390%]
.............[contention-diag] +3368s soak 34p/167t rss 12.4G pss 11.0G swap 1.8G majflt 181844 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 6 descendant rss 0.1G pss 0.1G | host avail 19.7G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.47/0.24 io 3.25 cpu 18.32 | cgroup 12.0G/max oom_kill 0 | free scratch 291.9G/45007903i tmp 29.7G/1015596i workspace 291.9G/45007903i | repeat-01 collected 26/26 workers (60615 items) tests 30108 done 5 failed | 24 in flight, oldest 234s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........................................................... [1393%]
........................................................................ [1396%]
........................................................................ [1400%]
..........................................[contention-diag] +3383s soak 35p/173t rss 12.5G pss 11.1G swap 1.8G majflt 182520 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.2G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 7 descendant rss 0.2G pss 0.1G | host avail 21.5G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.11/0.05 io 1.83 cpu 21.03 | cgroup 12.1G/max oom_kill 0 | free scratch 291.6G/45006676i tmp 29.7G/1015596i workspace 291.6G/45006676i | repeat-01 collected 26/26 workers (60615 items) tests 30339 done 5 failed | 25 in flight, oldest 249s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.............................. [1403%]
........................................................................ [1406%]
........................................................................ [1410%]
........................................................................ [1413%]
........................................................................ [1416%]
........................................................................ [1420%]
.....[contention-diag] +3398s soak 36p/179t rss 12.5G pss 11.1G swap 1.8G majflt 183050 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 8 descendant rss 0.2G pss 0.1G | host avail 19.6G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.02/0.01 io 1.71 cpu 11.87 | cgroup 12.1G/max oom_kill 0 | free scratch 291.0G/45005502i tmp 29.7G/1015596i workspace 291.0G/45005502i | repeat-01 collected 26/26 workers (60615 items) tests 30731 done 5 failed | 25 in flight, oldest 264s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................................... [1423%]
........................................................................ [1426%]
........................................................................ [1430%]
........................................................................ [1433%]
.....[contention-diag] +3414s soak 37p/168t rss 12.5G pss 11.1G swap 1.8G majflt 183336 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 9 descendant rss 0.2G pss 0.1G | host avail 19.4G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 1.81/1.45 io 4.89 cpu 15.72 | cgroup 12.3G/max oom_kill 0 | free scratch 290.6G/45004375i tmp 29.7G/1015597i workspace 290.6G/45004375i | repeat-01 collected 26/26 workers (60615 items) tests 31032 done 5 failed | 25 in flight, oldest 280s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
................................................................... [1436%]
........................................................................ [1440%]
........................................................................ [1443%]
........................................................................ [1446%]
........................................................................ [1449%]
........................................................................ [1453%]
........................................................................ [1456%]
.............................................................[contention-diag] +3429s soak 32p/162t rss 12.5G pss 11.1G swap 1.8G majflt 183651 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.7G, 4 descendant rss 0.2G pss 0.1G | host avail 25.0G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.5/0.35 io 3.93 cpu 18.31 | cgroup 12.1G/max oom_kill 0 | free scratch 289.7G/45002378i tmp 29.7G/1015597i workspace 289.7G/45002378i | repeat-01 collected 26/26 workers (60615 items) tests 31574 done 5 failed | 23 in flight, oldest 295s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
........... [1459%]
........................................................................ [1463%]
........................................................................ [1466%]
........................................................................ [1469%]
........................................................................ [1473%]
..............................................[contention-diag] +3444s soak 34p/170t rss 12.5G pss 11.1G swap 1.8G majflt 183799 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.7G, 6 descendant rss 0.1G pss 0.1G | host avail 23.1G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.1/0.07 io 4.4 cpu 18.08 | cgroup 12.2G/max oom_kill 0 | free scratch 289.6G/45000921i tmp 29.7G/1015597i workspace 289.6G/45000921i | repeat-01 collected 26/26 workers (60615 items) tests 31937 done 5 failed | 24 in flight, oldest 310s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
.......................... [1476%]
........................................................................ [1479%]
........................................................................ [1483%]
........................................................................ [1486%]
........................................................................ [1489%]
........................................................................ [1493%]
............................[contention-diag] +3460s soak 38p/170t rss 12.5G pss 11.1G swap 1.8G majflt 184021 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.8G, 10 descendant rss 0.1G pss 0.1G | host avail 21.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.26/0.25 io 5.03 cpu 19.7 | cgroup 12.3G/max oom_kill 0 | free scratch 289.5G/45000139i tmp 29.7G/1015597i workspace 289.5G/45000139i | scratch used 0.5G in 83964 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 32295 done 5 failed | 23 in flight, oldest 326s gw3 tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero | 1 hazardous kill call(s)
............................................ [1496%]
........................................................................ [1499%]
........................................................................ [1503%]
........................................................................ [1506%]
...................................................................[contention-diag] +3477s soak 35p/166t rss 12.5G pss 11.1G swap 1.8G majflt 184382 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.8G, 7 descendant rss 0.2G pss 0.1G | host avail 19.0G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 1.14/0.89 io 5.7 cpu 17.85 | cgroup 12.6G/max oom_kill 0 | free scratch 289.5G/44999245i tmp 29.7G/1015597i workspace 289.5G/44999245i | repeat-01 collected 26/26 workers (60615 items) tests 32660 done 5 failed | 24 in flight, oldest 281s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
..... [1509%]
........................................................................ [1513%]
........................................................................ [1516%]
........................................................................ [1519%]
.....................................................[contention-diag] +3493s soak 35p/170t rss 12.8G pss 11.3G swap 1.8G majflt 184776 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.8G, 7 descendant rss 0.4G pss 0.3G | host avail 17.8G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.95/0.72 io 4.48 cpu 19.42 | cgroup 12.3G/max oom_kill 0 | free scratch 289.3G/44998273i tmp 29.7G/1015597i workspace 289.3G/44998273i | repeat-01 collected 26/26 workers (60615 items) tests 32939 done 5 failed | 23 in flight, oldest 296s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 1 hazardous kill call(s)
................... [1523%]
........................................................................ [1526%]
........................................................................ [1529%]
........................................................................ [1533%]
.......................................[contention-diag] +3508s soak 36p/169t rss 12.7G pss 11.2G swap 1.8G majflt 184921 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.8G, 8 descendant rss 0.3G pss 0.2G | host avail 16.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.19/0.14 io 3.01 cpu 16.42 | cgroup 12.2G/max oom_kill 0 | free scratch 288.9G/44997559i tmp 29.7G/1015597i workspace 288.9G/44997559i | repeat-01 collected 26/26 workers (60615 items) tests 33214 done 5 failed | 24 in flight, oldest 312s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
................................. [1536%]
........................................................................ [1539%]
........................................................................ [1543%]
...........................................[contention-diag] +3523s soak 32p/159t rss 12.5G pss 11.1G swap 1.9G majflt 185147 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 4 descendant rss 0.2G pss 0.2G | host avail 22.1G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 1.1/0.03 io 2.67 cpu 14.3 | cgroup 12.0G/max oom_kill 0 | free scratch 288.5G/44997450i tmp 29.7G/1015597i workspace 288.5G/44997450i | repeat-01 collected 26/26 workers (60615 items) tests 33447 done 5 failed | 24 in flight, oldest 327s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
............................. [1546%]
........................................................................ [1549%]
.s...................................................................... [1553%]
........................................................................ [1556%]
........................................................................ [1559%]
.......[contention-diag] +3539s soak 39p/169t rss 12.7G pss 11.2G swap 1.9G majflt 185689 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.0G pss 10.7G, 11 descendant rss 0.4G pss 0.3G | host avail 24.8G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 2.55/0.0 io 3.91 cpu 15.65 | cgroup 12.1G/max oom_kill 0 | free scratch 286.7G/44996488i tmp 29.7G/1015597i workspace 286.7G/44996488i | repeat-01 collected 26/26 workers (60615 items) tests 33771 done 5 failed | 23 in flight, oldest 343s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
................................................................. [1563%]
........................................................................ [1566%]
........................................................................ [1569%]
........................................................................ [1573%]
....................[contention-diag] +3554s soak 33p/155t rss 12.6G pss 11.2G swap 1.9G majflt 185934 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.7G, 5 descendant rss 0.3G pss 0.2G | host avail 23.7G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 2.77/0.0 io 5.99 cpu 20.11 | cgroup 12.1G/max oom_kill 0 | free scratch 286.6G/44995539i tmp 29.7G/1015597i workspace 286.6G/44995539i | repeat-01 collected 26/26 workers (60615 items) tests 34056 done 5 failed | 24 in flight, oldest 358s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 4 hazardous kill call(s)
.................................................... [1576%]
........................................................................ [1579%]
........................................................................ [1583%]
...................................................................[contention-diag] +3570s soak 38p/172t rss 12.5G pss 11.0G swap 1.9G majflt 186267 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.7G, 10 descendant rss 0.1G pss 0.1G | host avail 23.8G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 3.04/0.0 io 5.68 cpu 20.28 | cgroup 12.0G/max oom_kill 0 | free scratch 286.2G/44994332i tmp 29.7G/1015597i workspace 286.2G/44994332i | repeat-01 collected 26/26 workers (60615 items) tests 34334 done 5 failed | 24 in flight, oldest 373s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 5 hazardous kill call(s)
..... [1586%]
........................................................................ [1589%]
........................................................................ [1592%]
........................................................................ [1596%]
........................................................................ [1599%]
........................................................................ [1602%]
...................................................[contention-diag] +3585s soak 32p/163t rss 12.5G pss 11.1G swap 1.9G majflt 186412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 21.4G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 3.11/0.0 io 5.34 cpu 19.2 | cgroup 12.0G/max oom_kill 0 | free scratch 286.2G/44993599i tmp 29.7G/1015597i workspace 286.2G/44993599i | scratch used 0.3G in 52567 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 34669 done 5 failed | 24 in flight, oldest 389s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
..................... [1606%]
........................................................................ [1609%]
........................................................................ [1612%]
........................................................................ [1616%]
........................................................................ [1619%]
........................................................................ [1622%]
........................................................................ [1626%]
........................................................................ [1629%]
...........[contention-diag] +3603s soak 32p/175t rss 12.5G pss 11.1G swap 1.8G majflt 186598 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 26.0G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 2.84/0.0 io 5.64 cpu 17.52 | cgroup 12.1G/max oom_kill 0 | free scratch 285.7G/44992109i tmp 29.7G/1015597i workspace 285.7G/44992109i | repeat-01 collected 26/26 workers (60615 items) tests 35278 done 5 failed | 22 in flight, oldest 406s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
............................................................. [1632%]
........................................................................ [1636%]
........................................................................ [1639%]
........................................................................ [1642%]
......................................................[contention-diag] +3618s soak 32p/172t rss 12.5G pss 11.1G swap 1.8G majflt 186958 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.2G, 26 worker rss 12.1G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 26.3G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.93/0.0 io 4.28 cpu 18.18 | cgroup 12.1G/max oom_kill 0 | free scratch 284.7G/44990991i tmp 29.7G/1015597i workspace 284.7G/44990991i | repeat-01 collected 26/26 workers (60615 items) tests 35604 done 5 failed | 24 in flight, oldest 422s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
.................. [1646%]
........................................................................ [1649%]
........................................................................ [1652%]
........................................................................ [1656%]
................................................[contention-diag] +3633s soak 32p/164t rss 12.5G pss 11.1G swap 1.8G majflt 187179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.1G pss 10.7G, 4 descendant rss 0.1G pss 0.1G | host avail 26.2G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 1.47/0.0 io 6.09 cpu 21.37 | cgroup 12.1G/max oom_kill 0 | free scratch 284.7G/44989940i tmp 29.7G/1015597i workspace 284.7G/44989940i | repeat-01 collected 26/26 workers (60615 items) tests 35890 done 5 failed | 24 in flight, oldest 437s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
........................ [1659%]
........................................................................ [1662%]
........................................................................ [1666%]
..............................................[contention-diag] +3649s soak 32p/173t rss 12.5G pss 11.0G swap 1.8G majflt 187433 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.1G pss 10.7G, 4 descendant rss 0.0G pss 0.0G | host avail 23.6G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.29/0.0 io 6.24 cpu 20.48 | cgroup 12.1G/max oom_kill 0 | free scratch 284.6G/44989074i tmp 29.7G/1015595i workspace 284.6G/44989074i | repeat-01 collected 26/26 workers (60615 items) tests 36113 done 5 failed | 23 in flight, oldest 452s gw10 tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed | 7 hazardous kill call(s)
.......................... [1669%]
........................................................................ [1672%]
........................................................................ [1676%]
........................................................................ [1679%]
........................................................................ [1682%]
.............[contention-diag] +3664s soak 30p/171t rss 12.5G pss 11.0G swap 1.8G majflt 187552 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.1G pss 10.8G, 2 descendant rss 0.0G pss 0.0G | host avail 23.4G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.07/0.0 io 4.59 cpu 19.94 | cgroup 12.1G/max oom_kill 0 | free scratch 284.4G/44988194i tmp 29.7G/1015597i workspace 284.4G/44988194i | repeat-01 collected 26/26 workers (60615 items) tests 36445 done 5 failed | 24 in flight, oldest 342s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
........................................................... [1686%]
........................................................................ [1689%]
........................................................................ [1692%]
........................................................................ [1696%]
........................................................................ [1699%]
.[contention-diag] +3679s soak 34p/182t rss 12.4G pss 11.0G swap 1.9G majflt 188179 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.1G pss 10.7G, 6 descendant rss 0.0G pss 0.0G | host avail 20.8G/62.7G swapfree 51.3G/64.0G oom_kill +0 | psi10 mem 0.85/0.69 io 6.37 cpu 16.87 | cgroup 12.1G/max oom_kill 0 | free scratch 284.3G/44986869i tmp 29.7G/1015597i workspace 284.3G/44986869i | repeat-01 collected 26/26 workers (60615 items) tests 36781 done 5 failed | 23 in flight, oldest 357s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 7 hazardous kill call(s)
....................................................................... [1702%]
........................................................................ [1706%]
....................................[contention-diag] +3695s soak 32p/176t rss 12.5G pss 11.0G swap 1.9G majflt 188538 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.1G pss 10.7G, 4 descendant rss 0.0G pss 0.0G | host avail 20.3G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.21/0.18 io 4.66 cpu 12.35 | cgroup 12.1G/max oom_kill 0 | free scratch 284.1G/44985101i tmp 29.7G/1015597i workspace 284.1G/44985101i | repeat-01 collected 26/26 workers (60615 items) tests 36961 done 5 failed | 24 in flight, oldest 372s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.................................... [1709%]
........................................................................ [1712%]
........................................................................ [1716%]
........................................................................ [1719%]
........[contention-diag] +3710s soak 34p/194t rss 12.6G pss 11.1G swap 1.9G majflt 188876 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 6 descendant rss 0.2G pss 0.1G | host avail 21.9G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.05/0.04 io 4.47 cpu 12.68 | cgroup 12.2G/max oom_kill 0 | free scratch 283.8G/44983866i tmp 29.7G/1015597i workspace 283.8G/44983866i | scratch used 0.4G in 81983 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 37198 done 5 failed | 24 in flight, oldest 388s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
................................................................ [1722%]
........................................................................ [1726%]
........................................................................ [1729%]
.....................................................s.................. [1732%]
............................................[contention-diag] +3728s soak 32p/180t rss 12.5G pss 11.1G swap 1.8G majflt 189625 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 4 descendant rss 0.0G pss 0.0G | host avail 18.6G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.43 cpu 13.12 | cgroup 12.2G/max oom_kill 0 | free scratch 283.5G/44982697i tmp 29.7G/1015597i workspace 283.5G/44982697i | repeat-01 collected 26/26 workers (60615 items) tests 37549 done 5 failed | 24 in flight, oldest 405s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................ [1735%]
........................................................................ [1739%]
........................................................................ [1742%]
.........................................[contention-diag] +3743s soak 38p/192t rss 12.6G pss 11.2G swap 1.8G majflt 189941 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 10 descendant rss 0.2G pss 0.1G | host avail 18.4G/62.7G swapfree 51.2G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.28 cpu 13.16 | cgroup 12.3G/max oom_kill 0 | free scratch 283.3G/44981971i tmp 29.7G/1015597i workspace 283.3G/44981971i | repeat-01 collected 26/26 workers (60615 items) tests 37759 done 5 failed | 23 in flight, oldest 420s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
............................... [1745%]
........................................................................ [1749%]
........................................................................ [1752%]
........................................................................ [1755%]
........................................................................ [1759%]
..........................[contention-diag] +3758s soak 34p/187t rss 12.6G pss 11.2G swap 1.9G majflt 190159 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 6 descendant rss 0.1G pss 0.1G | host avail 21.9G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 4.36 cpu 14.66 | cgroup 12.3G/max oom_kill 0 | free scratch 282.9G/44981108i tmp 29.7G/1015597i workspace 282.9G/44981108i | repeat-01 collected 26/26 workers (60615 items) tests 38104 done 5 failed | 24 in flight, oldest 436s gw25 tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed | 8 hazardous kill call(s)
.............................................. [1762%]
........................................................................ [1765%]
........................................................................ [1769%]
........................................................................ [1772%]
........................................................................ [1775%]
........................................................................ [1779%]
..[contention-diag] +3774s soak 37p/208t rss 12.7G pss 11.2G swap 1.8G majflt 190484 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 9 descendant rss 0.2G pss 0.1G | host avail 19.9G/62.7G swapfree 51.1G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 5.01 cpu 14.59 | cgroup 12.3G/max oom_kill 0 | free scratch 282.7G/44979660i tmp 29.7G/1015597i workspace 282.7G/44979660i | repeat-01 collected 26/26 workers (60615 items) tests 38520 done 5 failed | 24 in flight, oldest 315s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
...................................................................... [1782%]
........................................................................ [1785%]
..................................[contention-diag] +3789s soak 40p/199t rss 12.8G pss 11.3G swap 1.8G majflt 190805 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 12 descendant rss 0.3G pss 0.2G | host avail 19.3G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 1.27/1.12 io 4.03 cpu 9.39 | cgroup 12.4G/max oom_kill 0 | free scratch 282.4G/44976919i tmp 29.7G/1015597i workspace 282.4G/44976919i | repeat-01 collected 26/26 workers (60615 items) tests 38688 done 5 failed | 24 in flight, oldest 330s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
...................................... [1789%]
........................................................................ [1792%]
............................................................[contention-diag] +3804s soak 34p/187t rss 12.7G pss 11.2G swap 1.8G majflt 191333 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 6 descendant rss 0.2G pss 0.1G | host avail 22.5G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.31/0.27 io 3.53 cpu 14.28 | cgroup 12.4G/max oom_kill 0 | free scratch 282.3G/44976529i tmp 29.7G/1015597i workspace 282.3G/44976529i | repeat-01 collected 26/26 workers (60615 items) tests 38867 done 5 failed | 24 in flight, oldest 346s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............ [1795%]
...............s....................................................s... [1799%]
.........................[contention-diag] +3820s soak 34p/176t rss 12.7G pss 11.3G swap 1.8G majflt 192149 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 6 descendant rss 0.2G pss 0.2G | host avail 19.5G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.06/0.05 io 13.02 cpu 9.55 | cgroup 12.6G/max oom_kill 0 | free scratch 282.0G/44950823i tmp 29.7G/1015197i workspace 282.0G/44950823i | repeat-01 collected 26/26 workers (60615 items) tests 38971 done 5 failed | 24 in flight, oldest 361s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................................... [1802%]
........................................................................ [1805%]
........................................................[contention-diag] +3835s soak 33p/183t rss 12.7G pss 11.2G swap 1.9G majflt 192224 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 5 descendant rss 0.2G pss 0.2G | host avail 23.8G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 1.2/1.02 io 16.31 cpu 8.52 | cgroup 12.3G/max oom_kill 0 | free scratch 281.6G/44947143i tmp 29.7G/1015490i workspace 281.6G/44947143i | scratch used 0.1G in 23276 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 39136 done 5 failed | 23 in flight, oldest 377s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................ [1809%]
........................................................................ [1812%]
........................................................................ [1815%]
.......................[contention-diag] +3853s soak 35p/194t rss 12.8G pss 11.3G swap 1.9G majflt 192308 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 7 descendant rss 0.3G pss 0.3G | host avail 25.0G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.19/0.16 io 11.88 cpu 8.18 | cgroup 12.4G/max oom_kill 0 | free scratch 281.0G/44941763i tmp 29.7G/1015543i workspace 281.0G/44941763i | repeat-01 collected 26/26 workers (60615 items) tests 39331 done 5 failed | 23 in flight, oldest 394s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................. [1819%]
........................................................................ [1822%]
........................................................................ [1825%]
........................................................................ [1829%]
........................................................................ [1832%]
..........................................................[contention-diag] +3868s soak 36p/175t rss 12.8G pss 11.3G swap 1.9G majflt 192537 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 8 descendant rss 0.3G pss 0.3G | host avail 26.8G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.04/0.04 io 6.8 cpu 13.26 | cgroup 12.7G/max oom_kill 0 | free scratch 281.0G/44939054i tmp 29.7G/1015543i workspace 281.0G/44939054i | repeat-01 collected 26/26 workers (60615 items) tests 39724 done 5 failed | 22 in flight, oldest 410s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
.............. [1835%]
........................................................................ [1839%]
........................................................................ [1842%]
........................................................................ [1845%]
.....[contention-diag] +3884s soak 37p/183t rss 12.9G pss 11.4G swap 1.9G majflt 192738 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 9 descendant rss 0.4G pss 0.3G | host avail 22.6G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 14.82 cpu 10.49 | cgroup 13.1G/max oom_kill 0 | free scratch 280.2G/44911681i tmp 29.7G/1014906i workspace 280.2G/44911680i | repeat-01 collected 26/26 workers (60615 items) tests 39957 done 5 failed | 24 in flight, oldest 425s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
................................................................... [1849%]
........................................................................ [1852%]
.........................................[contention-diag] +3899s soak 36p/195t rss 12.9G pss 11.4G swap 1.9G majflt 193087 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 8 descendant rss 0.4G pss 0.3G | host avail 24.9G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 10.97 cpu 13.11 | cgroup 13.1G/max oom_kill 0 | free scratch 280.0G/44911335i tmp 29.7G/1015496i workspace 280.0G/44911335i | repeat-01 collected 26/26 workers (60615 items) tests 40130 done 5 failed | 23 in flight, oldest 441s gw12 tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed | 8 hazardous kill call(s)
............................... [1855%]
........................................................................ [1859%]
........................................................................ [1862%]
........................................................................ [1865%]
...[contention-diag] +3915s soak 38p/191t rss 12.8G pss 11.3G swap 1.9G majflt 193391 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 10 descendant rss 0.4G pss 0.3G | host avail 25.5G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 6.05 cpu 11.44 | cgroup 12.5G/max oom_kill 0 | free scratch 280.4G/44910315i tmp 29.7G/1015517i workspace 280.4G/44910315i | repeat-01 collected 26/26 workers (60615 items) tests 40389 done 5 failed | 23 in flight, oldest 116s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
..................................................................... [1869%]
........................................................................ [1872%]
........................................................................ [1875%]
........................................................................ [1878%]
....................................................[contention-diag] +3930s soak 33p/193t rss 12.5G pss 11.1G swap 1.9G majflt 193701 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 5 descendant rss 0.0G pss 0.0G | host avail 24.1G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.54/0.0 io 5.27 cpu 14.26 | cgroup 12.3G/max oom_kill 0 | free scratch 280.3G/44909035i tmp 29.7G/1015517i workspace 280.3G/44909035i | repeat-01 collected 26/26 workers (60615 items) tests 40732 done 5 failed | 24 in flight, oldest 131s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
.......s............ [1882%]
........................................................................ [1885%]
........................................................................ [1888%]
........................................................................ [1892%]
.....................................[contention-diag] +3945s soak 39p/202t rss 12.8G pss 11.3G swap 1.9G majflt 193969 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 11 descendant rss 0.3G pss 0.2G | host avail 25.8G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.15/0.0 io 6.29 cpu 16.74 | cgroup 12.6G/max oom_kill 0 | free scratch 280.0G/44907119i tmp 29.7G/1015530i workspace 280.0G/44907119i | repeat-01 collected 26/26 workers (60615 items) tests 40980 done 5 failed | 24 in flight, oldest 147s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
................................... [1895%]
........................................................................ [1898%]
........................................................................ [1902%]
........................................................................ [1905%]
........................................................................ [1908%]
..[contention-diag] +3961s soak 44p/173t rss 12.7G pss 11.2G swap 1.9G majflt 194609 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 16 descendant rss 0.2G pss 0.1G | host avail 23.3G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.03/0.0 io 4.22 cpu 13.61 | cgroup 12.5G/max oom_kill 0 | free scratch 280.0G/44907332i tmp 29.7G/1015545i workspace 280.0G/44907332i | scratch used 0.4G in 73305 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 41264 done 5 failed | 24 in flight, oldest 162s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
...................................................................... [1912%]
........................................................................ [1915%]
........................................................................ [1918%]
........................................................................ [1922%]
......................[contention-diag] +3978s soak 37p/170t rss 12.8G pss 11.3G swap 1.9G majflt 194829 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.8G, 9 descendant rss 0.2G pss 0.2G | host avail 28.7G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.12 cpu 13.69 | cgroup 12.6G/max oom_kill 0 | free scratch 279.8G/44905871i tmp 29.7G/1015546i workspace 279.8G/44905871i | repeat-01 collected 26/26 workers (60615 items) tests 41637 done 5 failed | 24 in flight, oldest 179s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
.................................................. [1925%]
........................................................................ [1928%]
........................................................................ [1932%]
........................................................................ [1935%]
........................................................................ [1938%]
..............................................................[contention-diag] +3994s soak 34p/177t rss 12.9G pss 11.4G swap 1.9G majflt 195278 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.8G, 6 descendant rss 0.4G pss 0.3G | host avail 28.4G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.79 cpu 19.75 | cgroup 12.8G/max oom_kill 0 | free scratch 279.8G/44902693i tmp 29.7G/1015546i workspace 279.8G/44902693i | repeat-01 collected 26/26 workers (60615 items) tests 42009 done 5 failed | 24 in flight, oldest 195s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
.......... [1942%]
........................................................................ [1945%]
........................................................................ [1948%]
........................................................................ [1952%]
........................................................................ [1955%]
........................................................................ [1958%]
..........[contention-diag] +4009s soak 33p/178t rss 12.9G pss 11.4G swap 1.9G majflt 195509 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.8G, 5 descendant rss 0.3G pss 0.2G | host avail 28.2G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.32/0.32 io 2.29 cpu 19.46 | cgroup 12.9G/max oom_kill 0 | free scratch 286.9G/44897300i tmp 29.7G/1015546i workspace 286.9G/44897300i | repeat-01 collected 26/26 workers (60615 items) tests 42385 done 5 failed | 23 in flight, oldest 210s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
.............................................................. [1962%]
........................................................................ [1965%]
........................................................................ [1968%]
........................................................................ [1972%]
........................................................................ [1975%]
......................[contention-diag] +4024s soak 36p/195t rss 13.0G pss 11.5G swap 1.9G majflt 195875 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 8 descendant rss 0.4G pss 0.3G | host avail 25.7G/62.7G swapfree 50.9G/64.0G oom_kill +0 | psi10 mem 0.08/0.08 io 3.1 cpu 18.92 | cgroup 12.9G/max oom_kill 0 | free scratch 286.9G/44888820i tmp 29.7G/1015546i workspace 286.9G/44888820i | repeat-01 collected 26/26 workers (60615 items) tests 42776 done 5 failed | 24 in flight, oldest 225s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 8 hazardous kill call(s)
.................................................. [1978%]
........................................................................ [1982%]
........................................................................ [1985%]
........................................................................ [1988%]
........................................................................ [1992%]
...[contention-diag] +4040s soak 35p/185t rss 13.0G pss 11.5G swap 1.9G majflt 196453 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 7 descendant rss 0.4G pss 0.4G | host avail 28.4G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.01/0.01 io 3.23 cpu 22.86 | cgroup 12.9G/max oom_kill 0 | free scratch 286.9G/44888872i tmp 29.7G/1015546i workspace 286.9G/44888872i | repeat-01 collected 26/26 workers (60615 items) tests 43110 done 5 failed | 23 in flight, oldest 241s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..................................................................... [1995%]
........................................................................ [1998%]
........................................................................ [2002%]
........................................................................ [2005%]
........................................................................ [2008%]
........................................................................ [2012%]
....................................................................[contention-diag] +4055s soak 36p/203t rss 13.0G pss 11.5G swap 1.9G majflt 196668 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 8 descendant rss 0.4G pss 0.3G | host avail 28.3G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.15/0.0 io 2.14 cpu 25.5 | cgroup 13.0G/max oom_kill 0 | free scratch 286.9G/44886903i tmp 29.7G/1015546i workspace 286.9G/44886903i | repeat-01 collected 26/26 workers (60615 items) tests 43623 done 5 failed | 24 in flight, oldest 256s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.... [2015%]
........................................................................ [2018%]
........................................................................ [2021%]
........................................................................ [2025%]
........................................................................ [2028%]
........................................................................ [2031%]
[contention-diag] +4070s soak 38p/201t rss 13.1G pss 11.6G swap 1.8G majflt 196921 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 10 descendant rss 0.4G pss 0.4G | host avail 25.3G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.03/0.0 io 0.85 cpu 18.87 | cgroup 13.0G/max oom_kill 0 | free scratch 286.9G/44885350i tmp 29.7G/1015546i workspace 286.9G/44885350i | repeat-01 collected 26/26 workers (60615 items) tests 43974 done 5 failed | 24 in flight, oldest 272s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
........................................................................ [2035%]
........................................................................ [2038%]
...........................................[contention-diag] +4086s soak 35p/206t rss 13.2G pss 11.5G swap 1.9G majflt 196995 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.8G, 7 descendant rss 0.5G pss 0.5G | host avail 22.9G/62.7G swapfree 51.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.17 cpu 11.86 | cgroup 13.2G/max oom_kill 0 | free scratch 286.5G/44883558i tmp 29.7G/1015546i workspace 286.5G/44883558i | scratch used 0.5G in 90558 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 44155 done 5 failed | 24 in flight, oldest 287s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................. [2041%]
........................................................................ [2045%]
........................................................................ [2048%]
......................[contention-diag] +4103s soak 36p/179t rss 13.2G pss 11.7G swap 1.9G majflt 197073 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 8 descendant rss 0.6G pss 0.5G | host avail 25.7G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 3.62/3.62 io 3.73 cpu 16.06 | cgroup 13.2G/max oom_kill 0 | free scratch 286.3G/44882772i tmp 29.7G/1015544i workspace 286.3G/44882772i | repeat-01 collected 26/26 workers (60615 items) tests 44369 done 5 failed | 24 in flight, oldest 304s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.................................................. [2051%]
........................................................................ [2055%]
........................................................................ [2058%]
........................................................................ [2061%]
........................................................................ [2065%]
..........................[contention-diag] +4119s soak 40p/193t rss 13.4G pss 11.8G swap 2.0G majflt 197130 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 12 descendant rss 0.8G pss 0.7G | host avail 24.0G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.89/0.89 io 2.34 cpu 18.46 | cgroup 13.5G/max oom_kill 0 | free scratch 286.3G/44881752i tmp 29.7G/1015546i workspace 286.3G/44881752i | repeat-01 collected 26/26 workers (60615 items) tests 44729 done 5 failed | 23 in flight, oldest 320s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.............................................. [2068%]
........................................................................ [2071%]
........................................................................ [2075%]
........................................................................ [2078%]
..............................................[contention-diag] +4134s soak 51p/211t rss 13.5G pss 11.9G swap 1.9G majflt 197340 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 23 descendant rss 0.8G pss 0.7G | host avail 23.2G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.18/0.18 io 1.36 cpu 19.89 | cgroup 13.5G/max oom_kill 0 | free scratch 286.3G/44881312i tmp 29.7G/1015546i workspace 286.3G/44881312i | repeat-01 collected 26/26 workers (60615 items) tests 45038 done 5 failed | 23 in flight, oldest 335s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......................... [2081%]
........................................................................ [2085%]
........................................................................ [2088%]
........................................................................ [2091%]
........................................................................ [2095%]
........................................................................ [2098%]
........................................................................ [2101%]
..............................[contention-diag] +4149s soak 39p/185t rss 13.5G pss 11.9G swap 1.9G majflt 197731 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 11 descendant rss 0.8G pss 0.7G | host avail 23.5G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.03/0.03 io 1.07 cpu 20.47 | cgroup 13.5G/max oom_kill 0 | free scratch 286.3G/44881206i tmp 29.7G/1015546i workspace 286.3G/44881206i | repeat-01 collected 26/26 workers (60615 items) tests 45491 done 5 failed | 21 in flight, oldest 351s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......................................... [2105%]
.....................................s.................................. [2108%]
........................................................................ [2111%]
........................................................................ [2115%]
........................................................................ [2118%]
........................................................................ [2121%]
........................................................................ [2125%]
.....................................................................[contention-diag] +4165s soak 38p/200t rss 13.5G pss 11.9G swap 1.9G majflt 197868 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 10 descendant rss 0.8G pss 0.7G | host avail 21.9G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.46 cpu 20.38 | cgroup 13.5G/max oom_kill 0 | free scratch 286.3G/44879491i tmp 29.7G/1015546i workspace 286.3G/44879491i | repeat-01 collected 26/26 workers (60615 items) tests 46064 done 5 failed | 22 in flight, oldest 366s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
... [2128%]
........................................................................ [2131%]
........................................................................ [2135%]
..............[contention-diag] +4180s soak 39p/199t rss 13.5G pss 11.9G swap 2.0G majflt 198220 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.8G, 11 descendant rss 0.8G pss 0.7G | host avail 22.1G/62.7G swapfree 50.5G/64.0G oom_kill +0 | psi10 mem 0.34/0.19 io 0.92 cpu 20.24 | cgroup 13.5G/max oom_kill 0 | free scratch 286.3G/44878695i tmp 29.7G/1015546i workspace 286.3G/44878695i | repeat-01 collected 26/26 workers (60615 items) tests 46220 done 5 failed | 20 in flight, oldest 381s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
.......................................................... [2138%]
........................................................................ [2141%]
........................................................................ [2145%]
........................................................................ [2148%]
........................................................................ [2151%]
........................................................................ [2155%]
............................[contention-diag] +4196s soak 37p/184t rss 13.4G pss 11.8G swap 2.0G majflt 198412 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.8G, 9 descendant rss 0.7G pss 0.7G | host avail 20.6G/62.7G swapfree 50.4G/64.0G oom_kill +0 | psi10 mem 0.06/0.03 io 1.11 cpu 18.32 | cgroup 13.4G/max oom_kill 0 | free scratch 286.1G/44877834i tmp 29.7G/1015546i workspace 286.1G/44877834i | repeat-01 collected 26/26 workers (60615 items) tests 46660 done 5 failed | 22 in flight, oldest 397s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
............................................ [2158%]
........................................................................ [2161%]
........................................................................ [2164%]
........................................................................ [2168%]
........................................................................ [2171%]
........................................................................ [2174%]
........................................................................ [2178%]
........................................................................ [2181%]
........................................................................ [2184%]
...............................................[contention-diag] +4211s soak 35p/183t rss 13.3G pss 11.8G swap 2.0G majflt 198820 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.8G, 7 descendant rss 0.7G pss 0.6G | host avail 26.3G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.21/0.06 io 1.15 cpu 17.32 | cgroup 13.4G/max oom_kill 0 | free scratch 286.0G/44877335i tmp 29.7G/1015546i workspace 286.0G/44877335i | scratch used 0.6G in 110103 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 47220 done 5 failed | 20 in flight, oldest 412s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
......................... [2188%]
........................................................................ [2191%]
........................................................................ [2194%]
........................................................................ [2198%]
........................................................................ [2201%]
...................................[contention-diag] +4228s soak 39p/193t rss 13.5G pss 11.9G swap 2.0G majflt 199148 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 11 descendant rss 0.9G pss 0.8G | host avail 27.7G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.41/0.0 io 0.75 cpu 25.31 | cgroup 13.6G/max oom_kill 0 | free scratch 286.0G/44876180i tmp 29.7G/1015545i workspace 286.0G/44876180i | repeat-01 collected 26/26 workers (60615 items) tests 47681 done 5 failed | 21 in flight, oldest 430s gw16 tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed | 9 hazardous kill call(s)
..................................... [2204%]
........................................................................ [2208%]
........................................................................ [2211%]
........................................................................ [2214%]
........................................................................ [2218%]
........................................................................ [2221%]
........................................................................ [2224%]
........................................................................ [2228%]
........................................................................ [2231%]
..............................[contention-diag] +4244s soak 37p/190t rss 13.6G pss 12.0G swap 2.0G majflt 199395 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 9 descendant rss 0.9G pss 0.8G | host avail 27.0G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.62/0.0 io 0.66 cpu 26.24 | cgroup 13.7G/max oom_kill 0 | free scratch 286.0G/44874584i tmp 29.7G/1015546i workspace 286.0G/44874584i | repeat-01 collected 26/26 workers (60615 items) tests 48312 done 5 failed | 20 in flight, oldest 305s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.......................................... [2234%]
........................................................................ [2238%]
........................................................................ [2241%]
........................................................................ [2244%]
........................................................................ [2248%]
........................................................................ [2251%]
.........[contention-diag] +4259s soak 40p/191t rss 13.7G pss 12.1G swap 2.0G majflt 199486 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 12 descendant rss 1.0G pss 0.9G | host avail 27.2G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.15/0.0 io 0.52 cpu 26.09 | cgroup 13.7G/max oom_kill 0 | free scratch 286.0G/44872456i tmp 29.7G/1015543i workspace 286.0G/44872456i | repeat-01 collected 26/26 workers (60615 items) tests 48742 done 5 failed | 21 in flight, oldest 320s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................................... [2254%]
........................................................................ [2258%]
........................................................................ [2261%]
........................................................................ [2264%]
........................................................................ [2268%]
........................................................................ [2271%]
..........................[contention-diag] +4274s soak 40p/185t rss 13.5G pss 11.9G swap 2.0G majflt 199581 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.3G pss 10.9G, 12 descendant rss 0.8G pss 0.7G | host avail 25.5G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.02/0.0 io 0.48 cpu 24.35 | cgroup 13.7G/max oom_kill 0 | free scratch 285.9G/44865400i tmp 29.7G/1015543i workspace 285.9G/44865400i | repeat-01 collected 26/26 workers (60615 items) tests 49175 done 5 failed | 19 in flight, oldest 335s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
.............................................. [2274%]
........................................................................ [2278%]
........................................................................ [2281%]
........................................................................ [2284%]
........................................................................ [2288%]
........................................................................ [2291%]
........................................................................ [2294%]
........................................................................ [2298%]
................[contention-diag] +4290s soak 38p/183t rss 13.6G pss 12.0G swap 2.0G majflt 199901 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.4G pss 10.9G, 10 descendant rss 0.8G pss 0.8G | host avail 25.9G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.24 cpu 25.56 | cgroup 13.9G/max oom_kill 0 | free scratch 285.9G/44870523i tmp 29.7G/1015543i workspace 285.9G/44870523i | repeat-01 collected 26/26 workers (60615 items) tests 49746 done 5 failed | 20 in flight, oldest 351s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
........................................................ [2301%]
........................................................................ [2304%]
........................................................................ [2307%]
...................................[contention-diag] +4305s soak 40p/174t rss 13.7G pss 12.1G swap 1.9G majflt 200265 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.4G pss 10.9G, 12 descendant rss 1.0G pss 0.9G | host avail 22.0G/62.7G swapfree 50.0G/64.0G oom_kill +0 | psi10 mem 0.36/0.0 io 0.18 cpu 23.92 | cgroup 14.0G/max oom_kill 0 | free scratch 285.9G/44869641i tmp 29.7G/1015543i workspace 285.9G/44869641i | repeat-01 collected 26/26 workers (60615 items) tests 50001 done 5 failed | 20 in flight, oldest 366s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
..................................... [2311%]
........................................................................ [2314%]
........................................................................ [2317%]
........................s..[contention-diag] +4321s soak 40p/188t rss 13.6G pss 11.9G swap 2.3G majflt 200636 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.1G pss 10.6G, 12 descendant rss 1.1G pss 1.0G | host avail 23.1G/62.7G swapfree 49.1G/64.0G oom_kill +0 | psi10 mem 7.16/5.61 io 6.8 cpu 11.16 | cgroup 13.8G/max oom_kill 0 | free scratch 284.5G/44867330i tmp 29.7G/1015543i workspace 284.5G/44867330i | repeat-01 collected 26/26 workers (60615 items) tests 50210 done 5 failed | 19 in flight, oldest 381s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................. [2321%]
........................................................................ [2324%]
........................................................................ [2327%]
........................................................................ [2331%]
........................................................................ [2334%]
............[contention-diag] +4336s soak 42p/193t rss 13.7G pss 12.1G swap 2.3G majflt 200904 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.1G pss 10.6G, 14 descendant rss 1.2G pss 1.1G | host avail 25.5G/62.7G swapfree 49.1G/64.0G oom_kill +0 | psi10 mem 1.51/1.13 io 4.53 cpu 15.21 | cgroup 13.9G/max oom_kill 0 | free scratch 284.3G/44866408i tmp 29.7G/1015543i workspace 284.3G/44866408i | scratch used 0.7G in 126389 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 50496 done 5 failed | 18 in flight, oldest 397s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................................ [2337%]
........................................................................ [2341%]
........................................................................ [2344%]
.........[contention-diag] +4354s soak 42p/199t rss 14.0G pss 12.3G swap 2.3G majflt 201716 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.1G pss 10.6G, 14 descendant rss 1.5G pss 1.4G | host avail 24.8G/62.7G swapfree 49.1G/64.0G oom_kill +0 | psi10 mem 1.24/0.22 io 1.29 cpu 17.2 | cgroup 14.4G/max oom_kill 0 | free scratch 284.2G/44865772i tmp 29.7G/1015545i workspace 284.2G/44865772i | repeat-01 collected 26/26 workers (60615 items) tests 50755 done 5 failed | 19 in flight, oldest 414s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
............................................................... [2347%]
........................................................................ [2351%]
........................................................................ [2354%]
........................................................................ [2357%]
........................................................................ [2361%]
.......[contention-diag] +4369s soak 38p/192t rss 13.7G pss 12.1G swap 2.3G majflt 202414 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.7G, 10 descendant rss 1.2G pss 1.1G | host avail 22.7G/62.7G swapfree 49.1G/64.0G oom_kill +0 | psi10 mem 0.45/0.04 io 0.63 cpu 19.33 | cgroup 14.1G/max oom_kill 0 | free scratch 284.1G/44864690i tmp 29.7G/1015545i workspace 284.1G/44864690i | repeat-01 collected 26/26 workers (60615 items) tests 51116 done 5 failed | 19 in flight, oldest 430s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................................................. [2364%]
........................................................................ [2367%]
........................................................................ [2371%]
........................................................................ [2374%]
.................................[contention-diag] +4384s soak 40p/186t rss 13.6G pss 11.9G swap 2.2G majflt 202564 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.3G pss 0.3G, 26 worker rss 12.2G pss 10.7G, 12 descendant rss 1.0G pss 0.9G | host avail 21.8G/62.7G swapfree 49.2G/64.0G oom_kill +0 | psi10 mem 0.27/0.18 io 1.14 cpu 16.98 | cgroup 14.0G/max oom_kill 0 | free scratch 284.0G/44863442i tmp 29.7G/1015544i workspace 284.0G/44863442i | repeat-01 collected 26/26 workers (60615 items) tests 51435 done 5 failed | 19 in flight, oldest 445s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
....................................... [2377%]
........................................................................ [2381%]
........................................................................ [2384%]
........................................................................ [2387%]
........................................................................ [2391%]
........................................[contention-diag] +4400s soak 42p/183t rss 13.7G pss 12.0G swap 2.2G majflt 202811 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.2G pss 10.7G, 14 descendant rss 1.1G pss 1.0G | host avail 20.0G/62.7G swapfree 49.2G/64.0G oom_kill +0 | psi10 mem 0.28/0.08 io 0.36 cpu 14.2 | cgroup 14.1G/max oom_kill 0 | free scratch 284.0G/44862992i tmp 29.7G/1015544i workspace 284.0G/44862992i | repeat-01 collected 26/26 workers (60615 items) tests 51805 done 5 failed | 17 in flight, oldest 461s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
................................ [2394%]
........................................................................ [2397%]
........................................................................ [2401%]
...................................................[contention-diag] +4415s soak 46p/196t rss 13.6G pss 11.9G swap 2.4G majflt 202959 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.0G pss 10.5G, 18 descendant rss 1.3G pss 1.2G | host avail 19.0G/62.7G swapfree 48.9G/64.0G oom_kill +0 | psi10 mem 0.23/0.08 io 0.51 cpu 13.48 | cgroup 13.3G/max oom_kill 0 | free scratch 284.0G/44861722i tmp 29.7G/1015543i workspace 284.0G/44861722i | repeat-01 collected 26/26 workers (60615 items) tests 52033 done 5 failed | 18 in flight, oldest 476s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 9 hazardous kill call(s)
..................... [2404%]
........................................................................ [2407%]
........................................................................ [2411%]
........................................................................ [2414%]
........................................................................ [2417%]
........................................................................ [2421%]
........................................................................ [2424%]
........................................................................ [2427%]
........................................................................ [2431%]
..............[contention-diag] +4430s soak 36p/172t rss 13.3G pss 11.7G swap 2.5G majflt 203152 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.9G pss 10.4G, 8 descendant rss 1.0G pss 1.0G | host avail 19.7G/62.7G swapfree 48.9G/64.0G oom_kill +0 | psi10 mem 1.03/1.0 io 2.72 cpu 16.3 | cgroup 13.1G/max oom_kill 0 | free scratch 283.9G/44860430i tmp 29.7G/1015542i workspace 283.9G/44860430i | repeat-01 collected 26/26 workers (60615 items) tests 52607 done 5 failed | 17 in flight, oldest 491s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.......................................................... [2434%]
........................................................................ [2437%]
........................................................................ [2441%]
........................................................................ [2444%]
........................................................................ [2447%]
........................................................................ [2450%]
........................................................................ [2454%]
........................................................................ [2457%]
........................................................................ [2460%]
........................................................................ [2464%]
........................................................................ [2467%]
........................................................................ [2470%]
..................................[contention-diag] +4446s soak 40p/175t rss 13.4G pss 11.7G swap 2.5G majflt 203731 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 11.9G pss 10.4G, 12 descendant rss 1.0G pss 1.0G | host avail 18.5G/62.7G swapfree 49.1G/64.0G oom_kill +0 | psi10 mem 0.2/0.2 io 1.65 cpu 14.13 | cgroup 13.1G/max oom_kill 0 | free scratch 283.8G/44858389i tmp 29.7G/1015544i workspace 283.8G/44858389i | repeat-01 collected 26/26 workers (60615 items) tests 53507 done 5 failed | 17 in flight, oldest 507s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
...................................... [2474%]
........................................................................ [2477%]
........................................................................ [2480%]
........................................................................ [2484%]
........................................................................ [2487%]
........................................................................ [2490%]
........................................................................ [2494%]
..............................[contention-diag] +4461s soak 39p/181t rss 13.4G pss 11.8G swap 2.5G majflt 204219 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.0G pss 10.5G, 11 descendant rss 1.1G pss 1.0G | host avail 19.3G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.05/0.04 io 3.14 cpu 13.33 | cgroup 13.1G/max oom_kill 0 | free scratch 283.6G/44857541i tmp 29.7G/1015544i workspace 283.6G/44857540i | scratch used 0.3G in 49604 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 53918 done 5 failed | 15 in flight, oldest 522s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.......................................... [2497%]
........................................................................ [2500%]
........................................................................ [2504%]
........................................................................ [2507%]
........................................................................ [2510%]
........................................................................ [2514%]
..............................[contention-diag] +4479s soak 40p/169t rss 13.4G pss 11.8G swap 2.5G majflt 204293 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.0G pss 10.5G, 12 descendant rss 1.1G pss 1.0G | host avail 18.6G/62.7G swapfree 50.8G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.85 cpu 12.04 | cgroup 13.2G/max oom_kill 0 | free scratch 283.1G/44855874i tmp 29.7G/1015544i workspace 283.1G/44855874i | repeat-01 collected 26/26 workers (60615 items) tests 54443 done 5 failed | 16 in flight, oldest 540s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.......................................... [2517%]
........................................................................ [2520%]
........................................................................ [2524%]
........................................................................ [2527%]
........................................................................ [2530%]
........................................................................ [2534%]
........................[contention-diag] +4494s soak 38p/182t rss 13.5G pss 11.9G swap 2.4G majflt 204507 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.0G pss 10.5G, 10 descendant rss 1.2G pss 1.1G | host avail 21.7G/62.7G swapfree 51.4G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 3.99 cpu 13.75 | cgroup 13.2G/max oom_kill 0 | free scratch 285.5G/44859374i tmp 29.7G/1015542i workspace 285.5G/44859374i | repeat-01 collected 26/26 workers (60615 items) tests 54861 done 5 failed | 14 in flight, oldest 555s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................................ [2537%]
.............................................................s.......... [2540%]
........................................................................ [2544%]
........................................................................ [2547%]
........................................................................ [2550%]
.......................[contention-diag] +4510s soak 37p/170t rss 13.4G pss 11.8G swap 2.5G majflt 204803 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.0G pss 10.5G, 9 descendant rss 1.1G pss 1.0G | host avail 26.3G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.43 cpu 17.54 | cgroup 13.3G/max oom_kill 0 | free scratch 285.4G/44858319i tmp 29.7G/1015544i workspace 285.4G/44858320i | repeat-01 collected 26/26 workers (60615 items) tests 55236 done 5 failed | 16 in flight, oldest 570s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................................. [2554%]
........................................................................ [2557%]
........................................................................ [2560%]
........................................................................ [2564%]
........................................................................ [2567%]
........................................................................ [2570%]
........................................................................ [2574%]
........................................................................ [2577%]
........................................[contention-diag] +4525s soak 38p/174t rss 13.5G pss 11.9G swap 2.4G majflt 204959 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.0G pss 10.5G, 10 descendant rss 1.2G pss 1.1G | host avail 23.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.29 cpu 13.75 | cgroup 13.4G/max oom_kill 0 | free scratch 285.4G/44857069i tmp 29.7G/1015544i workspace 285.4G/44857069i | repeat-01 collected 26/26 workers (60615 items) tests 55821 done 5 failed | 15 in flight, oldest 586s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
................................ [2580%]
........................................................................ [2584%]
........................................................................ [2587%]
........................................................................ [2590%]
........................................................................ [2593%]
........................................................................ [2597%]
..........[contention-diag] +4540s soak 38p/174t rss 13.5G pss 11.9G swap 2.4G majflt 205516 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.3G, 26 worker rss 12.0G pss 10.5G, 10 descendant rss 1.2G pss 1.1G | host avail 22.7G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.25 cpu 16.07 | cgroup 13.4G/max oom_kill 0 | free scratch 285.3G/44856885i tmp 29.7G/1015544i workspace 285.3G/44856885i | repeat-01 collected 26/26 workers (60615 items) tests 56239 done 5 failed | 15 in flight, oldest 601s gw22 tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection | 10 hazardous kill call(s)
.............................................................. [2600%]
........................................................................ [2603%]
........................................................................ [2607%]
........................................................................ [2610%]
........................................................................ [2613%]
........................................................................ [2617%]
........................................................................ [2620%]
........................................................................ [2623%]
...................................s..............[contention-diag] +4556s soak 38p/175t rss 12.8G pss 11.1G swap 2.4G majflt 205816 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.0G pss 10.5G, 10 descendant rss 0.4G pss 0.3G | host avail 21.9G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.48 cpu 17.3 | cgroup 12.7G/max oom_kill 0 | free scratch 289.1G/44867133i tmp 29.7G/1015544i workspace 289.1G/44867133i | repeat-01 collected 26/26 workers (60615 items) tests 56846 done 5 failed | 15 in flight, oldest 100s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
...................... [2627%]
........................................................................ [2630%]
........................................................................ [2633%]
........................................................................ [2637%]
............................................[contention-diag] +4571s soak 42p/172t rss 13.1G pss 11.4G swap 2.4G majflt 205953 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.0G pss 10.5G, 14 descendant rss 0.7G pss 0.6G | host avail 20.1G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.32 cpu 15.39 | cgroup 12.9G/max oom_kill 0 | free scratch 289.0G/44866243i tmp 29.7G/1015544i workspace 289.0G/44866243i | repeat-01 collected 26/26 workers (60615 items) tests 57114 done 5 failed | 15 in flight, oldest 116s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
............................ [2640%]
........................................................................ [2643%]
........................................................................ [2647%]
........................................................................ [2650%]
........................................................................ [2653%]
........................................................................ [2657%]
.....................................[contention-diag] +4586s soak 37p/160t rss 12.7G pss 11.1G swap 2.4G majflt 205978 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.0G pss 10.5G, 9 descendant rss 0.4G pss 0.3G | host avail 21.2G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.13 cpu 14.39 | cgroup 12.6G/max oom_kill 0 | free scratch 288.7G/44866102i tmp 29.7G/1015544i workspace 288.7G/44866102i | scratch used 0.3G in 62886 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 57427 done 5 failed | 13 in flight, oldest 131s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
................................... [2660%]
........................................................................ [2663%]
........................................................................ [2667%]
........................................................................ [2670%]
...................s.................................................... [2673%]
........................................................................ [2677%]
........................................................................ [2680%]
........................................................................ [2683%]
......................................................[contention-diag] +4604s soak 36p/157t rss 12.6G pss 11.0G swap 2.4G majflt 206190 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.0G pss 10.5G, 8 descendant rss 0.2G pss 0.2G | host avail 24.1G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.2 cpu 14.89 | cgroup 12.6G/max oom_kill 0 | free scratch 291.1G/44880127i tmp 29.7G/1015544i workspace 291.1G/44880127i | repeat-01 collected 26/26 workers (60615 items) tests 58140 done 5 failed | 10 in flight, oldest 148s gw20 tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds | 10 hazardous kill call(s)
.................. [2687%]
........................................................................ [2690%]
........................................................................ [2693%]
........................................................................ [2697%]
........................................................................ [2700%]
......................................[contention-diag] +4619s soak 36p/162t rss 12.6G pss 11.0G swap 2.4G majflt 206521 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.0G pss 10.5G, 8 descendant rss 0.2G pss 0.2G | host avail 23.6G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.71 cpu 15.0 | cgroup 12.6G/max oom_kill 0 | free scratch 291.1G/44879855i tmp 29.7G/1015544i workspace 291.1G/44879855i | repeat-01 collected 26/26 workers (60615 items) tests 58502 done 5 failed | 10 in flight, oldest 57s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
.................................. [2703%]
........................................................................ [2707%]
........................................................................ [2710%]
........................................................................ [2713%]
.....................[contention-diag] +4635s soak 32p/156t rss 12.4G pss 10.7G swap 2.4G majflt 207029 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.0G pss 10.3G, 4 descendant rss 0.0G pss 0.0G | host avail 24.0G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.72 cpu 15.55 | cgroup 12.5G/max oom_kill 0 | free scratch 290.7G/44879500i tmp 29.7G/1015544i workspace 290.7G/44879500i | repeat-01 collected 26/26 workers (60615 items) tests 58737 done 5 failed | 8 in flight, oldest 73s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
................................................... [2717%]
........................................................................ [2720%]
........................................................................ [2723%]
........................................................................ [2727%]
........................................................................ [2730%]
............................[contention-diag] +4650s soak 37p/158t rss 12.6G pss 10.9G swap 2.3G majflt 208402 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.1G pss 10.5G, 9 descendant rss 0.1G pss 0.0G | host avail 21.0G/62.7G swapfree 51.5G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 2.66 cpu 16.26 | cgroup 12.5G/max oom_kill 0 | free scratch 290.6G/44877917i tmp 29.7G/1015543i workspace 290.6G/44877917i | repeat-01 collected 26/26 workers (60615 items) tests 59120 done 5 failed | 7 in flight, oldest 88s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
............................................ [2733%]
........................................................................ [2736%]
..........................................[contention-diag] +4665s soak 34p/158t rss 12.6G pss 11.0G swap 2.4G majflt 208534 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.1G pss 10.5G, 6 descendant rss 0.1G pss 0.1G | host avail 21.7G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.05 cpu 16.58 | cgroup 12.6G/max oom_kill 0 | free scratch 290.6G/44877971i tmp 29.7G/1015544i workspace 290.6G/44877971i | repeat-01 collected 26/26 workers (60615 items) tests 59290 done 5 failed | 7 in flight, oldest 103s gw21 tests/test_launcher_origin.py::test_every_launcher_call_passes_origin_explicitly | 10 hazardous kill call(s)
.............................. [2740%]
........................................................................ [2743%]
........................................................................ [2746%]
........................................................................ [2750%]
..............................................[contention-diag] +4681s soak 33p/153t rss 12.5G pss 10.7G swap 2.3G majflt 209331 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.1G pss 10.3G, 5 descendant rss 0.0G pss 0.0G | host avail 22.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.6 cpu 18.38 | cgroup 12.5G/max oom_kill 0 | free scratch 290.6G/44878018i tmp 29.7G/1015542i workspace 290.6G/44878018i | repeat-01 collected 26/26 workers (60615 items) tests 59590 done 5 failed | 6 in flight, oldest 68s gw12 tests/workspace_provider/test_primary_writable_store_import_boundary.py::test_writable_store_resolution_importers_match_the_audited_allowlist | 10 hazardous kill call(s)
.......................... [2753%]
........................................................................ [2756%]
........................................................................ [2760%]
........................................................................ [2763%]
.............................ssss....................................... [2766%]
........................................................................ [2770%]
..[contention-diag] +4696s soak 33p/151t rss 12.6G pss 11.0G swap 2.3G majflt 209617 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.1G pss 10.5G, 5 descendant rss 0.1G pss 0.1G | host avail 20.9G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 1.29 cpu 14.99 | cgroup 12.7G/max oom_kill 0 | free scratch 290.6G/44875296i tmp 29.7G/1015541i workspace 290.6G/44875296i | repeat-01 collected 26/26 workers (60615 items) tests 59977 done 5 failed | 5 in flight, oldest 6s gw16 tests/tool/test_detach_watchdog.py::test_watchdog_reports_ended_join_monitor | 10 hazardous kill call(s)
...................................................................... [2773%]
........................................................................ [2776%]
........................................................................ [2780%]
........................................................................ [2783%]
........................................................................ [2786%]
........................................................................ [2790%]
........................................................................ [2793%]
........................................................................ [2796%]
....................[contention-diag] +4712s soak 32p/150t rss 12.5G pss 10.9G swap 2.3G majflt 209886 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G, 26 worker rss 12.1G pss 10.6G, 4 descendant rss 0.0G pss 0.0G | host avail 20.6G/62.7G swapfree 51.6G/64.0G oom_kill +0 | psi10 mem 0.0/0.0 io 0.64 cpu 13.85 | cgroup 12.6G/max oom_kill 0 | free scratch 290.6G/44868342i tmp 29.7G/1015540i workspace 290.6G/44868342i | scratch used 0.5G in 86985 entries (truncated) | repeat-01 collected 26/26 workers (60615 items) tests 60560 done 5 failed | 1 in flight, oldest 1s gw20 tests/tool/test_handoff.py::test_handoff_secret_never_reaches_proc_row | 10 hazardous kill call(s)
...........................................          [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________ test_empty_panel_escape_follows_the_hide_panel_binding ____________
[gw4] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

fut = <coroutine object AcePage.press at 0x7fbf1f14d560>, timeout = 5.0

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

../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/asyncio/tasks.py:520: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:366: in press
    await self._pilot.press(*keys)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/pilot.py:83: in press
    await self._app._press_keys(keys)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/app.py:1994: in _press_keys
    await wait_for_idle(0)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/_wait.py:29: in wait_for_idle
    await sleep(SLEEP_GRANULARITY)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

delay = 0.02, result = None

    async def sleep(delay, result=None):
        """Coroutine that completes after a given time (in seconds)."""
        if delay <= 0:
            await __sleep0()
            return result
    
        loop = events.get_running_loop()
        future = loop.create_future()
        h = loop.call_later(delay,
                            futures._set_result_unless_cancelled,
                            future, result)
        try:
>           return await future
                   ^^^^^^^^^^^^
E           asyncio.exceptions.CancelledError

../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/asyncio/tasks.py:665: CancelledError

The above exception was the direct cause of the following exception:

prebuilt_command_line_grammar = CommandLineGrammar(_handle=<sase_core_rs.CommandLineGrammar object at 0x7fbf1f17c330>)

    async def test_empty_panel_escape_follows_the_hide_panel_binding(
        prebuilt_command_line_grammar: object,
    ) -> None:
        """A rebound hide key leaves empty-line Escape to vim's INSERT handling."""
        from unittest.mock import patch as mock_patch
    
        from sase.ace.testing import AcePage, make_patch
        from sase.ace.tui import AceApp
        from sase.ace.tui.keymaps import load_keymap_registry
    
        with (
            mock_patch.object(AceApp, "_load_agents"),
            mock_patch.object(AceApp, "_load_axe_status"),
        ):
            async with AcePage(query="test_feature", patches=[make_patch()]) as page:
                page.app._command_line_grammar = prebuilt_command_line_grammar
                page.app._keymap_registry = load_keymap_registry(
                    {"keymaps": {"command_line": {"hide_panel": "f8"}}}
                )
                page.app.action_open_command_line()
                await page.expect_modal("CommandLineScreen")
    
>               await asyncio.wait_for(page.press("escape"), timeout=5.0)

tests/ace/tui/command_line/test_panel_shell_pilot.py:137: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/asyncio/tasks.py:519: in wait_for
    async with timeouts.timeout(timeout):
               ^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Timeout [expired]>
exc_type = <class 'asyncio.exceptions.CancelledError'>
exc_val = CancelledError(), exc_tb = <traceback object at 0x7fbf1c51c740>

    async def __aexit__(
        self,
        exc_type: Optional[Type[BaseException]],
        exc_val: Optional[BaseException],
        exc_tb: Optional[TracebackType],
    ) -> Optional[bool]:
        assert self._state in (_State.ENTERED, _State.EXPIRING)
    
        if self._timeout_handler is not None:
            self._timeout_handler.cancel()
            self._timeout_handler = None
    
        if self._state is _State.EXPIRING:
            self._state = _State.EXPIRED
    
            if self._task.uncancel() <= self._cancelling and exc_type is exceptions.CancelledError:
                # Since there are no new cancel requests, we're
                # handling this.
>               raise TimeoutError from exc_val
E               TimeoutError

../../../../../../share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/asyncio/timeouts.py:115: TimeoutError
________________ test_config_jump_preserves_collapsed_sections _________________
[gw11] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f2350d47650>

    async def test_config_jump_preserves_collapsed_sections(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        _patch_loaders(monkeypatch)
>       async with AcePage() as page:
                   ^^^^^^^^^

tests/ace/tui/test_config_pane_widget_jump.py:127: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:330: in __aenter__
    await settle_helpers.settle_pilot(self._pilot)
src/sase/ace/testing/settle.py:43: in settle_pilot
    await pause(pilot, 0)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/pilot.py:530: in pause
    await self._wait_for_screen()
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Pilot app=AceApp(title='sase tui (v0.18.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})>
timeout = 30.0

    async def _wait_for_screen(self, timeout: float = 30.0) -> bool:
        """Wait for the current screen and its children to have processed all pending events.
    
        Args:
            timeout: A timeout in seconds to wait.
    
        Returns:
            `True` if all events were processed. `False` if an exception occurred,
            meaning that not all events could be processed.
    
        Raises:
            WaitForScreenTimeout: If the screen and its children didn't finish processing within the timeout.
        """
        try:
            screen = self.app.screen
        except Exception:
            return False
        children = [self.app, *screen.walk_children(with_self=True)]
        count = 0
        count_zero_event = asyncio.Event()
    
        def decrement_counter() -> None:
            """Decrement internal counter, and set an event if it reaches zero."""
            nonlocal count
            count -= 1
            if count == 0:
                # When count is zero, all messages queued at the start of the method have been processed
                count_zero_event.set()
    
        # Increase the count for every successful call_later
        for child in children:
            if child.call_later(decrement_counter):
                count += 1
    
        if count:
            # Wait for the count to return to zero, or a timeout, or an exception
            wait_for = [
                asyncio.create_task(count_zero_event.wait()),
                asyncio.create_task(self.app._exception_event.wait()),
            ]
            _, pending = await asyncio.wait(
                wait_for,
                timeout=timeout,
                return_when=asyncio.FIRST_COMPLETED,
            )
    
            for task in pending:
                task.cancel()
    
            timed_out = len(wait_for) == len(pending)
            if timed_out:
>               raise WaitForScreenTimeout(
                    "Timed out while waiting for widgets to process pending messages."
                )
E               textual.pilot.WaitForScreenTimeout: Timed out while waiting for widgets to process pending messages.

/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/pilot.py:512: WaitForScreenTimeout
[contention-diag] +4728s soak 2p/2t rss 0.4G pss 0.4G swap 0.1G majflt 16979 | 1 parent rss 0.0G pss 0.0G, 1 controller rss 0.4G pss 0.4G | host avail 32.6G/62.7G swapfree 53.7G/64.0G oom_kill +0 | psi10 mem 0.39/0.0 io 0.57 cpu 15.71 | cgroup 2.1G/max oom_kill 0 | free scratch 290.5G/44859040i tmp 29.7G/1015539i workspace 290.5G/44859040i | repeat-01 collected 26/26 workers (60615 items) tests 60615 done 5 failed | 10 hazardous kill call(s)
____________ test_tab_reaches_every_field_and_scrolls_it_into_view _____________
[gw22] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

    async def test_tab_reaches_every_field_and_scrolls_it_into_view() -> None:
        request = _tall_request()
        panel = GateInputPanel(request)
        app = StyledGateTestApp()
        async with app.run_test(size=(120, 40)) as pilot:
            app.push_screen(panel)
>           await _wait_for_panel(pilot, 120, 40, panel)

tests/ace/tui/test_gate_input_panel_layout.py:123: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/test_gate_input_panel_layout.py:77: in _wait_for_panel
    await wait_for_terminal(pilot, width, height)
tests/ace/tui/_custom_gate_modal_helpers.py:134: in wait_for_terminal
    await wait_for(pilot, terminal_matches)
src/sase/ace/testing/wait.py:98: in wait_for
    await _poll_until(
src/sase/ace/testing/wait.py:66: in _poll_until
    await settle()
src/sase/ace/testing/settle.py:43: in settle_pilot
    await pause(pilot, 0)
/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/pilot.py:530: in pause
    await self._wait_for_screen()
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <Pilot app=StyledGateTestApp(title='StyledGateTestApp', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})>
timeout = 30.0

    async def _wait_for_screen(self, timeout: float = 30.0) -> bool:
        """Wait for the current screen and its children to have processed all pending events.
    
        Args:
            timeout: A timeout in seconds to wait.
    
        Returns:
            `True` if all events were processed. `False` if an exception occurred,
            meaning that not all events could be processed.
    
        Raises:
            WaitForScreenTimeout: If the screen and its children didn't finish processing within the timeout.
        """
        try:
            screen = self.app.screen
        except Exception:
            return False
        children = [self.app, *screen.walk_children(with_self=True)]
        count = 0
        count_zero_event = asyncio.Event()
    
        def decrement_counter() -> None:
            """Decrement internal counter, and set an event if it reaches zero."""
            nonlocal count
            count -= 1
            if count == 0:
                # When count is zero, all messages queued at the start of the method have been processed
                count_zero_event.set()
    
        # Increase the count for every successful call_later
        for child in children:
            if child.call_later(decrement_counter):
                count += 1
    
        if count:
            # Wait for the count to return to zero, or a timeout, or an exception
            wait_for = [
                asyncio.create_task(count_zero_event.wait()),
                asyncio.create_task(self.app._exception_event.wait()),
            ]
            _, pending = await asyncio.wait(
                wait_for,
                timeout=timeout,
                return_when=asyncio.FIRST_COMPLETED,
            )
    
            for task in pending:
                task.cancel()
    
            timed_out = len(wait_for) == len(pending)
            if timed_out:
>               raise WaitForScreenTimeout(
                    "Timed out while waiting for widgets to process pending messages."
                )
E               textual.pilot.WaitForScreenTimeout: Timed out while waiting for widgets to process pending messages.

/tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/textual/pilot.py:512: WaitForScreenTimeout
_ test_tab_completes_after_root_print_command_option[sase bead sh-sase bead show ] _
[gw5] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw5/test_tab_completes_after_root_0')
typed = 'sase bead sh', expected = 'sase bead show '

    @pytest.mark.parametrize(
        ("typed", "expected"),
        [
            ("sase bead sh", "sase bead show "),
            ("sase -p bead sh", "sase -p bead show "),
            ("sase --print-command bead sh", "sase --print-command bead show "),
        ],
    )
    def test_tab_completes_after_root_print_command_option(
        tmp_path: Path, typed: str, expected: str
    ) -> None:
        fpath_dir = tmp_path / "fpath"
        fpath_dir.mkdir()
        _write_live_script(fpath_dir)
    
>       captured = _pty_capture_completion(tmp_path, fpath_dir, typed)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/completion/test_zsh_smoke.py:230: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/completion/test_zsh_smoke.py:602: in _pty_capture_completion
    screen = _read_until(fd, marker.encode(), timeout=5.0)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

fd = 14, needle = b'__SASE_CAPTURE_105413799907997__', timeout = 5.0

    def _read_until(fd: int, needle: bytes, timeout: float = 5.0) -> bytes:
        buf = b""
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            remaining = deadline - time.monotonic()
            ready, _, _ = select.select([fd], [], [], max(0.0, remaining))
            if not ready:
                continue
            try:
                chunk = os.read(fd, 4096)
            except OSError:
                break
            if not chunk:
                break
            buf += chunk
            if needle in buf:
                return buf
>       raise TimeoutError(f"timed out waiting for {needle!r}; got {buf!r}")
E       TimeoutError: timed out waiting for b'__SASE_CAPTURE_105413799907997__'; got b'sase bead sh'

tests/completion/test_zsh_smoke.py:669: TimeoutError
_________ test_dynamic_completion_does_not_leak_extendedglob_to_shell __________
[gw5] linux -- Python 3.12.13 /tmp/sase-1rq-runtime-py312/bin/python

tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-0/popen-gw5/test_dynamic_completion_does_n0')

    def test_dynamic_completion_does_not_leak_extendedglob_to_shell(
        tmp_path: Path,
    ) -> None:
        fpath_dir = tmp_path / "fpath"
        fpath_dir.mkdir()
        _write_live_script(fpath_dir)
        bin_dir, _calls = _write_logged_fixture_sase(
            tmp_path,
            "zzz-completion-fixture\tFixture bead",
        )
    
>       captured = _pty_capture_completion(
            tmp_path,
            fpath_dir,
            "sase bead show zzz",
            bin_dir=bin_dir,
        )

tests/completion/test_zsh_smoke.py:446: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/completion/test_zsh_smoke.py:602: in _pty_capture_completion
    screen = _read_until(fd, marker.encode(), timeout=5.0)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

fd = 14, needle = b'__SASE_CAPTURE_105597422721071__', timeout = 5.0

    def _read_until(fd: int, needle: bytes, timeout: float = 5.0) -> bytes:
        buf = b""
        deadline = time.monotonic() + timeout
        while time.monotonic() < deadline:
            remaining = deadline - time.monotonic()
            ready, _, _ = select.select([fd], [], [], max(0.0, remaining))
            if not ready:
                continue
            try:
                chunk = os.read(fd, 4096)
            except OSError:
                break
            if not chunk:
                break
            buf += chunk
            if needle in buf:
                return buf
>       raise TimeoutError(f"timed out waiting for {needle!r}; got {buf!r}")
E       TimeoutError: timed out waiting for b'__SASE_CAPTURE_105597422721071__'; got b'sase bead show zzz'

tests/completion/test_zsh_smoke.py:669: TimeoutError
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

tests/ace/tui/test_agent_archive_controller_prewarm.py::test_early_open_paints_loading_and_queues_until_gate
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/inspect.py:3076: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    params = OrderedDict((param.name, param) for param in parameters)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_run_policies.py::test_builtin_cd_submit_pins_and_renders_block
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored in: <coroutine object CommandLineScreenSubmissionMixin._record_local_history.<locals>._record at 0x7f9c12e6a790>
  
  Traceback (most recent call last):
    File "<string>", line 1, in <lambda>
  KeyError: '__import__'
  
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.
    warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))

tests/ace/tui/modals/test_memory_pane_review.py::test_unreviewed_dots_only_newer_than_watermark
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:472: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    __dict__['method_calls'] = _CallList()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_grammar_ready_refreshes_open_empty_panel_without_a_keystroke
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/typing.py:2187: RuntimeWarning: coroutine '_recheck_grammar_key' was never awaited
    def cast(typ, val):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/modals/test_glossary_preview_modal.py::test_glossary_modal_follows_references_and_goes_back
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/rich/text.py:144: RuntimeWarning: coroutine 'CommandLineScreenSubmissionMixin._submit_worker' was never awaited
    def __init__(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_panel_shell_pilot.py::test_real_input_history_filters_prefix_and_resets_new_walk
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/unittest/mock.py:2217: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    def __init__(self, name, parent):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_completion_fixes.py::test_cursor_move_during_a_fetch_drops_the_result
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pathlib.py:369: RuntimeWarning: coroutine '_record_history_async.<locals>._record' was never awaited
    path = os.fspath(arg)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/command_line/test_transcript_blocks_actions.py::test_y_and_Y_copy_output_and_command
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/config/loading.py:92: RuntimeWarning: coroutine 'CommandLineScreen._load_tail_worker' was never awaited
    payload = binding(
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_controller_generations.py::test_worker_publishes_display_snapshot_for_project_banners
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/util/pump_tasks.py:94: RuntimeWarning: coroutine '_run_archive_request' was never awaited
    registry_names = set()
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_collapsed_panel_selection.py::test_no_tribe_collapsed_focus_is_not_confused_with_missing_focus
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/copy.py:118: RuntimeWarning: coroutine 'open_archive_chooser.<locals>._hydrate_and_present' was never awaited
    def deepcopy(x, memo=None, _nil=[]):
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_agent_archive_restore_proof.py::test_proof_async_submit_hydrates_off_thread
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/core/content_layout_wire.py:330: RuntimeWarning: coroutine 'AgentMetadataPagerMixin._open_agent_metadata_pager' was never awaited
    formats=tuple(str(item) for item in raw.get("formats", [])),
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
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=1784212) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/completion/test_zsh_smoke.py: 19 warnings
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/pty.py:95: DeprecationWarning: This process (pid=1784012) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/footprint/test_tui.py::test_bump_resets_cached_state_after_fork
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/footprint/test_tui.py:110: DeprecationWarning: This process (pid=1784538) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/agents_sync/test_publication_job.py::test_sigkilled_publisher_leaves_request_active_and_releases_locks
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=1784026) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

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

tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_macro_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/macro/workflow_runner.py:477: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_runner_workspace_reclone.py::TestRecreateEndToEnd::test_forced_verify_failure_recreates_then_launch_prep_succeeds changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:888: DeprecationWarning: This process (pid=1784012) is multi-threaded, use of fork() may lead to deadlocks in the child.

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

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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

tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end
  /tmp/sase-1rq-runtime-py312/lib/python3.12/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/history/test_continuation_replay_hydration_retry.py::test_retry_then_fork_replay_end_to_end changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
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
  /home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib/python3.12/multiprocessing/popen_fork.py:66: DeprecationWarning: This process (pid=1784561) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
609.57s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
453.03s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
452.49s call     tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed
444.00s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
430.16s setup    tests/test_agent_artifact_dismissed_save_audit.py::test_dismissed_agent_save_sites_are_reviewed
391.30s call     tests/ace/tui/modals/test_deck_picker_modal.py::test_deck_picker_lowercase_picks_this_panel_capital_picks_other
342.12s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
330.28s call     tests/test_project_display_presentation_audit.py::test_display_fallback_exemptions_name_existing_sites_and_rationales
320.85s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
317.57s call     tests/test_project_display_presentation_audit.py::test_project_display_name_fallback_lives_only_in_chokepoint
313.82s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
298.06s call     tests/test_markdown_print_width.py::test_source_modules_preserve_markdown_width_policy
264.80s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
214.25s call     tests/instructions/test_invoke_boundary.py::test_only_boundary_calls_provider_invoke
186.43s call     tests/instructions/test_invoke_boundary.py::test_allowlist_entries_still_exist
182.45s call     tests/history/test_continuation_replay_hydration_basic.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
178.62s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
166.09s call     tests/ace/tui/test_config_edit_modal_layout_widget.py::test_expanded_class_tracks_multiline_preview_and_reset_states
163.65s call     tests/pager/test_perf_gates.py::test_large_document_memory_ceiling
150.16s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
=========================== short test summary info ============================
FAILED tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding
FAILED tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_preserves_collapsed_sections
FAILED tests/ace/tui/test_gate_input_panel_layout.py::test_tab_reaches_every_field_and_scrolls_it_into_view
FAILED tests/completion/test_zsh_smoke.py::test_tab_completes_after_root_print_command_option[sase bead sh-sase bead show ]
FAILED tests/completion/test_zsh_smoke.py::test_dynamic_completion_does_not_leak_extendedglob_to_shell
==== 5 failed, 60590 passed, 21 skipped, 111 warnings in 4728.38s (1:18:48) ====
[contention-diag] +4737s soak 1p/1t rss 0.0G pss 0.0G swap 0.0G majflt 504 | 1 parent rss 0.0G pss 0.0G | host avail 31.6G/62.7G swapfree 53.8G/64.0G oom_kill +0 | psi10 mem 0.17/0.0 io 0.44 cpu 7.06 | cgroup 1.7G/max oom_kill 0 | free scratch 290.5G/44859040i tmp 29.7G/1015539i workspace 290.5G/44859040i | repeat-01 collected 26/26 workers (60615 items) tests 60615 done 5 failed | 10 hazardous kill call(s)
[contention-diag] stopped (stopped by the harness) after 4737s, 307 samples, 0 signal(s); peaks: cgroup_current 14.4G, min_free_scratch 279.8G, min_free_tmp 29.6G, min_free_workspace 279.8G, min_inodes_scratch 44855874, min_inodes_tmp 1014875, min_inodes_workspace 44855874, min_mem_available 6.5G, min_swap_free 48.1G, oom_kill_delta 0, pressure_memory_full 45.25, pswpin_delta 3304572, pswpout_delta 4879033, scratch_bytes 0.7G, soak_procs 51, soak_pss 12.3G, soak_rss 14.0G, soak_swap 2.5G, soak_threads 292

contention tally: 5 node(s) failed across 1 repeat(s) in 4736.7s; red repeats: 1
  1/1  tests/ace/tui/command_line/test_panel_shell_pilot.py::test_empty_panel_escape_follows_the_hide_panel_binding  (repeats 1)
  1/1  tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_preserves_collapsed_sections  (repeats 1)
  1/1  tests/ace/tui/test_gate_input_panel_layout.py::test_tab_reaches_every_field_and_scrolls_it_into_view  (repeats 1)
  1/1  tests/completion/test_zsh_smoke.py::test_dynamic_completion_does_not_leak_extendedglob_to_shell  (repeats 1)
  1/1  tests/completion/test_zsh_smoke.py::test_tab_completes_after_root_print_command_option[sase bead sh-sase bead show ]  (repeats 1)
per-repeat failure records: .pytest_cache/sase-contention
contention diagnostics: .pytest_cache/sase-contention/diagnostics

