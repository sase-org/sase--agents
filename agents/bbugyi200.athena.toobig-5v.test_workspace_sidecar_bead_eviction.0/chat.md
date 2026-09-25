# Chat History - ace-run (toobig-5v.test_workspace_sidecar_bead_eviction.0)

- **TIMESTAMP:** 2026-09-22 22:58:22 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5v.test_workspace_sidecar_bead_eviction.0

## Prompt

%id(test_workspace_sidecar_bead_eviction.0, clan=toobig-5v)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `tests/test_bead/test_workspace_sidecar_bead_eviction.py` file up into multiple files? Use your best
%wait:toobig-5v.test_agent_loader_dedup_merge.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 869-line `tests/test_bead/test_workspace_sidecar_bead_eviction.py` is now three files, each under 500 lines, with all 18 tests preserved verbatim:

- [workspace_sidecar_eviction_test_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/test_bead/workspace_sidecar_eviction_test_helpers.py) (231 lines) — shared seeds, rescue/bundle assertions, clone/publish recorders, and `_WORKSPACE_NUM`. Named without the `test_` prefix so pytest doesn't collect it, matching the existing `*_test_helpers.py` convention.
- [test_workspace_sidecar_eviction_plans.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/test_bead/test_workspace_sidecar_eviction_plans.py) (420 lines) — the 10 generic/plans-sidecar tests (quarantine, publication, remote integration, retry/rescue, rebase conflicts, non-origin upstream).
- [test_workspace_sidecar_eviction_beads.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/test_bead/test_workspace_sidecar_eviction_beads.py) (278 lines) — the 8 bead-store tests plus the store-dir/repo-root discovery and unknown-count safety tests.

The split is by sidecar kind (generic plans clone vs. bead store), since that's the axis the tests themselves branch on. Each test module carries its own copy of the small `_clear_publication_memo` autouse fixture, because an autouse fixture in the helpers module would not apply across modules. The original file was deleted. A diff of test names before/after confirms all 18 survived.

Verification: `just fmt` is clean, and all 18 tests pass in the project venv (18 passed in ~9s). `sase tool run check` passes every gate through terminology but stops at `lint (symvision)` on `delete_paths_in_background` in `src/sase/_linked_repo_workspaces.py`. That failure is pre-existing and unrelated — I confirmed it fails identically with my changes stashed, and my diff touches only `tests/test_bead/`. It already has a task bead, so I corroborated it as `sase-16l` (+7) rather than filing a duplicate.
