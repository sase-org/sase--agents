# Chat History - ace-run (toobig-5v.run_agent_runner_setup.0)

- **TIMESTAMP:** 2026-09-22 21:06:44 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5v.run_agent_runner_setup.0

## Prompt

%id(run_agent_runner_setup.0, clan=toobig-5v)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/axe/run_agent_runner_setup.py` file up into multiple files? Use your best
%wait:toobig-5v.keybinding_bindings.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 791-line `src/sase/axe/run_agent_runner_setup.py` is now five files, all under 500 lines:

- [run_agent_runner_setup.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/run_agent_runner_setup.py) (58 lines) — facade re-exporting the historical import surface; existing `from ... import` sites in `run_agent_runner`, `launch`, `bootstrap`, and `workspace_identity` needed no changes.
- [run_agent_runner_setup_workspace.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/run_agent_runner_setup_workspace.py) (189) — occupancy guard, workspace prep/entry, SDD base-SHA capture.
- [run_agent_runner_setup_linked_repos.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/run_agent_runner_setup_linked_repos.py) (263) — linked-repo preparation, clone re-creation, refresh.
- [run_agent_runner_setup_prompt.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/run_agent_runner_setup_prompt.py) (188) — prompt preprocessing, deferred-fork expansion, banner/output-var helpers.
- [run_agent_runner_setup_meta.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/axe/run_agent_runner_setup_meta.py) (216) — artifacts dir, agent meta, retry chain, telemetry, home marker.

Two judgment calls: `_guard_workspace_not_occupied` became public `guard_workspace_not_occupied`, since symvision forbids cross-file private imports; and test `patch()` targets plus the marker-mutation audit entries were retargeted to the submodule where each lookup now happens (patch strings only, no test-logic changes).

Verification: 76 tests across all directly affected suites pass (setup, workspace, linked-repos, audit, occupancy, reclone, fork, identity, bootstrap-errors). `sase tool run check` passes every gate except `symvision`, which fails on `delete_paths_in_background` in the untouched `_linked_repo_workspaces.py` — I confirmed via stash that it fails identically on the pristine tree, as do some full-runner integration tests that need the harness env. Those are pre-existing findings, not from this split.
