# Chat History - ace-run (toobig-5r.test_ace_tmux.0)

- **TIMESTAMP:** 2026-09-21 23:25:42 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5r.test_ace_tmux.0

## Prompt

%id(test_ace_tmux.0, clan=toobig-5r)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/main/test_ace_tmux.py` file up into multiple files? Use your best
%wait:toobig-5r.test_muse_provider_core.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 852-line `tests/main/test_ace_tmux.py` into four files, all well under 500 lines:

- [ace_tmux_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/main/ace_tmux_helpers.py) (160 lines) – shared `FakeTmux`, `SocketTmuxRunner`, `completed_process`, `launch_args`, and `patch_screenshot_request_dir`, following the repo's `*_helpers.py` convention.
- [test_ace_tmux_launch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/main/test_ace_tmux_launch.py) (153 lines, 7 tests) – window claiming, session selection, missing-tmux exit.
- [test_ace_tmux_relaunch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/main/test_ace_tmux_relaunch.py) (225 lines, 8 tests) – relaunch argv rewriting and profiling env vars.
- [test_ace_tmux_windows.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/tests/main/test_ace_tmux_windows.py) (383 lines, 5 tests) – real-tmux isolated-socket integration tests.

The original file was removed. Test bodies are verbatim copies; only the `_`-prefixed helper names were made importable, and the one autouse screenshot-dir fixture is now a shared helper invoked by a thin fixture in each file.

Verification: all 20 tests pass in the project venv, and `sase tool run check` (all lint gates + diff-scoped tests) succeeded.
