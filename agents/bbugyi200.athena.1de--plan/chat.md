# Chat History - ace-run (1de--plan)

- **TIMESTAMP:** 2026-11-17 10:09:11 EST
- **MODEL:** claude/opus
- **AGENT:** 1de--plan

**Plan:** /home/bryan/.sase/plans/202611/install_scoped_update_status_snapshot.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/install_scoped_update_status_snapshot.md`

> # Scope the update-status snapshot to the running install
> ## Problem
> ACE's top-bar badge (`updates: ⬆1`) and the Update panel rows (`,U`) read one
> machine-wide cache, `~/.sase/updates/status_snapshot.json`
> (`src/sase/updates/cache.py::_cache_path`). That snapshot's contents depend on the
> install. For editable installs, each `OutdatedComponent` records the checkout's
> `source_root`, and "behind upstream" is a property of that one checkout.
> Any `sase tui` started from a different install writes its own install's verdict into
> that same file. Examples are a workspace `.venv` used by GC census or soak runs, or a
> screenshot or perf harness. That happens through `get_cached_update_status()` (startup

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Why are we showing that a sase update is available, but the `,U` keymap reports
differently? See the ~/tmp/screenshots/20261117_100311.png screenshot for context. Is
this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. %m:@xlarge

## Response

Tracing `,U` from the leader keymap into the update action, and comparing it with the `updates: ⬆1` header indicator.

Comparing the header's cached update status with the `,U` preview path. Next I'll check the live cache on disk to see which component it flags.

Root cause found: the shared update-status cache file was written by a TUI running from another agent workspace (`sase_22`). Checking which process did that and how the TUI's update check runs.

I have the full root cause. Writing the plan now.

Plan validated; submitting it for approval.

The two disagree because they read different installs. The `⬆1` badge was describing a different copy of sase, not the one your TUI runs from. This is a real bug and worth fixing. I've submitted a plan for it, which you'll get to approve.

**What happened**
- The badge and the `,U` panel rows read one shared cache file, `~/.sase/updates/status_snapshot.json`. Any TUI on the machine can write to it.
- The `sase-1t3.9` GC census soak (the "SLEEPING 2H CENSUS" agent in your screenshot) started its own TUI at 09:56:41. That TUI runs from the `sase_22` workspace's `.venv`, not your installed copy, but it uses your real `~/.sase`.
- At 09:57:15 it wrote its own result into the shared file. The `sase_22` checkout is at `4adc535e2`, one commit behind `origin/master`, so the file now lists one update with `source_root` pointing at `sase_22`.
- Your TUI runs from `~/projects/github/sase-org/sase`, which is already at the newest commit (`ea7916d7a`). It read that file and re-checked the update against `sase_22` itself, which really is still behind. So it kept the entry and showed `⬆1`.
- `,U` → Everything doesn't use the cache. It checks your own install from scratch, finds it current, and shows "Everything in the captured comprehensive update is already current." That answer is correct.

Each side is right about its own install. The bug is that they share one cache file. Worse, the two TUIs can keep overwriting each other's result for as long as the soak runs.

**What the plan changes** (`sase_plan_install_scoped_update_status_snapshot.md`, small)
1. **One cache file per install**, in `src/sase/updates/cache.py`. The filename gets a short hash of the running interpreter's environment path (the uv tool environment for your install, `<workspace>/.venv` for a workspace run). The file also records that path, and a TUI ignores a file recorded by a different install. The old shared file is deleted, and per-install files untouched for more than 7 days are cleaned up when a new snapshot is written.
2. **Refresh the badge after a no-op `,U`**, in `src/sase/ace/tui/actions/update_run.py`. When the fresh check finds nothing to update, the badge re-checks the cache and drops entries that are no longer behind, so it can't keep contradicting the toast.
3. Tests for both, in `tests/test_update_status_snapshot.py` and `tests/ace/tui/test_update_run_actions.py`.

**Until the fix lands:** the badge will flip back and forth while the census soak is running. It isn't worth intervening, because the badge stops being wrong once the soak finishes.
