#fork:toobig-58.runner_workspace.0--plan
%model:grok-4.6
%effort:xhigh

%xprompts_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-09-11T19:17:13.602035+00:00 |
| **Finished** | 2026-09-11T19:18:07.941854+00:00 |
| **Elapsed** | 52s of a 45m 0s budget |
| **Output** | 861 bytes · evidence refs: `file:monitor-diagnostic-manifest:dwqaa6h8j7em`, `file:monitor-retained-log:dwqaa6h8j7em`, `file:monitor-stage:lint-mypy-2019438-1789154287632547384-ea64721f` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show dwqaa6h8j7em --all-lines` |

**Why this was monitored:** Verify the runner_workspace split with whole-repo lint and scoped tests

## Your next action

The previous turn split src/sase/axe/runner_workspace.py (846 lines) into a facade plus three implementation modules, all <=500 lines:

- src/sase/axe/runner_workspace.py — public facade re-exporting prepare_workspace, prepare_launch_workspace_repos, clear_stale_git_index_lock, git_index_lock_path
- src/sase/axe/runner_workspace_prepare.py — checkout/clean, agents-sidecar lock, launch eviction, unpublished-commit orchestrator
- src/sase/axe/runner_workspace_sidecar.py — sidecar publication, push, recovery refs
- src/sase/axe/runner_workspace_beads.py — bead-store protection

Tests that imported or patched private helpers were updated to the defining modules. Targeted tests already passed (52). mypy on the four modules passed.

Handle the just check result:
1. If it passed: use /sase_final and reply to the user summarizing the split and file sizes.
2. If it failed because of our split (runner_workspace* files, their tests, or new public helpers): fix, re-verify, then reply. Use /sase_monitor for another just check if it will take long.
3. If it failed only on pre-existing Symvision private-import findings in update_handler_*, plugins/cli_*, tmux_agent/cli.py, or pipe_handler.py: do not change those files. Run any just check stages that did not execute after that failure (typically toobig, validate, test-scoped). If those pass, use /sase_final and reply summarizing the split. Mention the pre-existing Symvision failure only if it blocked just check.

Do not mention the ephemeral workspace directory name in the user-facing reply. Keep the historical sase.axe.runner_workspace import surface working.
%xprompts_enabled:true