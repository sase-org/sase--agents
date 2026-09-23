# Chat History - ace-run (toobig-5v.runner_workspace_prepare.0)

- **TIMESTAMP:** 2026-09-22 21:29:30 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5v.runner_workspace_prepare.0

## Prompt

%id(runner_workspace_prepare.0, clan=toobig-5v)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/axe/runner_workspace_prepare.py` file up into multiple files? Use your best
%wait:toobig-5v.run_agent_runner_setup.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. Split the 778-line `src/sase/axe/runner_workspace_prepare.py` into five modules, all under 500 lines:

- [runner_workspace_prepare.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/runner_workspace_prepare.py:1) (324 lines) — single-pass orchestration (`prepare_workspace`, `_prepare_workspace_locked`, `clear_stale_git_index_lock`); re-exports the moved names so the existing import surface is unchanged.
- [runner_workspace_heal.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/runner_workspace_heal.py:1) (259 lines) — self-heal ladder (rescue, checkout/sync rungs, postcondition verify).
- [runner_workspace_protection.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/runner_workspace_protection.py:1) (166 lines) — agents-sync guard, sidecar protection, rescue-before-eviction, launch repo setup.
- [runner_workspace_reclone.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/runner_workspace_reclone.py:1) (67 lines) — re-creation retry.
- [runner_workspace_errors.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/runner_workspace_errors.py:1) (37 lines) — shared `WorkspacePreparationError`.

Two judgment calls worth knowing:

1. Shared helpers are now public (`heal_sync_rung`, `protect_unpushed_sidecar_commits`, etc.) instead of `_`-prefixed. The symvision gate forbids cross-file private imports, so keeping them private was not an option. I updated the four test references accordingly; `get_vcs_provider` still lives in `prepare`, so existing mock targets there keep working.
2. Verification: 84 tests across the 7 workspace-preparation test files pass, and every `just check` gate passes except one pre-existing symvision failure (`delete_paths_in_background` in untouched `_linked_repo_workspaces.py`), which I confirmed fails identically on pristine HEAD and corroborated on the existing bead `sase-16l` rather than filing a duplicate.

The change was submitted via the finalizer declaration for host commit.
