# Chat History - ace-run (toobig-al.fs_watcher.0)

- **TIMESTAMP:** 2026-11-22 21:53:33 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-al.fs_watcher.0

## Prompt

%auto
%id(fs_watcher.0, clan=toobig-al)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/util/fs_watcher.py` file into multiple files? Use your best
%wait:toobig-al.surface_tokens.0
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

Split `fs_watcher.py` (702 lines) into a facade plus four private modules, each under 500 lines.

New layout in [src/sase/ace/tui/util](src/sase/ace/tui/util):

- [fs_watcher.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/fs_watcher.py:1) (18 lines): facade only, re-exports `ArtifactWatcher`, `DEFAULT_EVENT_MASK`, `MAX_INOTIFY_WATCHES`, `DEFAULT_COALESCE_S`, `DEFAULT_DISPATCH_DEADLINE_S`, `PIPE_IDLE_FALLBACK_S`. No `_private` re-exports.
- [_fs_watcher_common.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/_fs_watcher_common.py:1) (114 lines): shared public helpers `IN_*` (11 inotify constants), `is_ignored_watch_name`, `load_libc`.
- [_fs_watcher_core.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/_fs_watcher_core.py:1) (210 lines): `WatcherCore` base with `__init__`, `stats`, `_pending_select_timeout`, `_note_relevant_paths`, `_path_is_consumed`, `_maybe_flush`, `_dispatch_change`; owns `DEFAULT_*`/`PIPE_*` and private `_callback_accepts_positional`.
- [_fs_watcher_watches.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/_fs_watcher_watches.py:1) (205 lines): `WatcherWatches(WatcherCore)` with `ensure_watches`, `prune_agent_dir_watches`, `_add_watch_path`, `_remove_watch`, startup/shard iteration, `_add_watch_tree`; owns `MAX_INOTIFY_WATCHES` and private `_watch_key`, `_path_is_dir`.
- [_fs_watcher_runner.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/util/_fs_watcher_runner.py:1) (222 lines): `ArtifactWatcher(WatcherWatches)` with `start`, `stop`, `_loop`, `_collect_relevant_events`; owns private `_EVENT_HEADER`.

No new module imports a `_`-prefixed name from another; all cross-module imports (`is_ignored_watch_name`, `load_libc`, `IN_*`, `WatcherCore`, `WatcherWatches`) are public.

Tests retargeted (facade no longer exposes privates):

- `test_fs_watcher_coalesce.py`: `IN_*`/`is_ignored_watch_name` from `_fs_watcher_common`.
- `test_fs_watcher_watches.py`: `iter_startup_ace_run_shard_watch_paths` from `sase.core.agent_artifact_shards`; `MAX_INOTIFY_WATCHES` patch retargeted to `sase.ace.tui.util._fs_watcher_watches.MAX_INOTIFY_WATCHES`. The `ArtifactWatcher._add_watch_path` patch still works via inheritance.
- `_fs_watcher_helpers.py` and `_prompt_catalog_watchers.py`: `_libc` → `load_libc` from `_fs_watcher_common`.

Verification observed:

- `just _lint-symvision`: pass (`All public/private classes/functions are used properly!`).
- `just _lint-mypy`: pass (`Success: no issues found in 6719 source files`).
- `just _lint-toobig`: pass (all files within 700 info limit).
- `sase tool run check`: ran twice. First run failed only on ruff formatting in the retargeted test (fixed). Second run completed the lint stages but the scoped test lane reports 11 failures in files this split did not touch (`test_event_handlers_artifact_dirty_flags.py`, `test_startup_stopwatch_live_update.py`), e.g. `UnboundLocalError: axe_file_opens` in `src/sase/ace/tui/actions/event_refresh/_auto_refresh_surface_axe.py:120`. All 37 fs_watcher-specific tests pass.

Declaration submitted: commit for the fs_watcher split work.
