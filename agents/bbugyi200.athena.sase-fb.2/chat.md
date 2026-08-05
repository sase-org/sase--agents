# Chat History - ace-run (sase-fb.2)

- **TIMESTAMP:** 2026-08-05 16:26:39 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-fb.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-fb, bead=sase-fb.2)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-fb.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-fb.2 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-fb.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now let me write the implementation.

Now wire the guard into the eviction path.

Now the workflow runner's graceful failure path:

Now verify the tests fail against the pre-change code:

Meanwhile, let me review the final diff.

I'll wait for the run to finish.

Implementation and tests are in place; I'm waiting on a full `just test` run to confirm whether the one failing test (`test_concurrent_bead_mutations_wait_past_the_old_lock_timeout`) is a pre-existing load-sensitive flake. I'll report when it finishes.

Lint is clean. Recording the flake as a follow-up and closing the bead.

Done. Bead `sase-fb.2` (the `evict` phase) is implemented and closed — and I confirmed the close itself actually reached the canonical remote (0 unpushed commits in the beads sidecar), which is the very failure this epic is about.

## What changed

**`src/sase/axe/runner_workspace.py`**
- **Sidecar-layout discovery.** New `_workspace_bead_store_dirs()` finds the sidecar-repos stores at `<workspace>/sase/repos/beads` (split-beads clone root) and `<workspace>/sase/repos/plans/beads` (combined sidecar), alongside the existing `<repo_root>/beads` and in-tree layouts. `_beads_dir_belongs_to_repo` is replaced by `_bead_store_repo_root()`, which resolves each store's *own* git root and accepts it when it is the workspace repo **or a clone nested inside it** — previously the guard bailed out and protected nothing for the sidecar layout. Per-store publish/rescue moved into `_protect_bead_store()`, so the recovery ref lands in the store's own repo rather than the primary workspace repo.
- **Eviction barrier.** `prepare_launch_workspace_repos` now runs the guard with `refuse_on_unpublished=True` *before* `clear_workspace_repos()` (only for `workspace_num > 1`, the only case that evicts). It publishes synchronously first; if commits remain, it retains the recovery ref and raises the new `WorkspaceBeadEvictionRefused` instead of warning and proceeding — the `sase/repos` → `.sase/trash` rename never happens. `prepare_workspace` keeps its original warn-and-proceed behavior.

**`src/sase/axe/run_workflow_runner.py`** — catches the refusal and fails workspace prep cleanly (the agent runner already treats a raise as fatal).

**`tests/test_bead/test_workspace_sidecar_bead_eviction.py`** (new) — the refusal case (clone neither trashed nor re-cloned, recovery ref exists and is named in the stderr diagnostic), the published-clone case (evicted normally, no publish attempt, so the barrier doesn't wedge routine launches), and layout-discovery coverage.

## Verification
- Confirmed the barrier test fails against pre-change behavior: with the guard call disabled, `test_eviction_refuses_to_trash_unpublished_sidecar_bead_commits` fails while the rest pass.
- `just lint` clean (ruff, mypy, symvision, toobig).
- `just test`: 25799 passed, **1 failure** — `test_concurrent_bead_mutations_wait_past_the_old_lock_timeout`. It's a pre-existing load-sensitive flake (workers hit the 12s bead-mutation lock timeout under xdist contention; passes in isolation in ~4s) in the bead mutation lock path, untouched by this diff. Recorded as a `PROPOSED FOLLOW-UP:` note on the bead for the land agent.

The code changes are uncommitted in the working tree — say the word if you want them committed.

Bead is closed. Committing the changes.

Committed and pushed.

- **Bead `sase-fb.2`**: already closed (2026-08-05T20:24:23Z, resolution `done`), with the flaky-test follow-up recorded as a `PROPOSED FOLLOW-UP:` note for the land agent.
- **Commit `d1b6f01a9`** — `fix(axe): refuse to evict workspace sidecar clones holding unpublished bead commits` — staged the three files explicitly (`runner_workspace.py`, `run_workflow_runner.py`, and the new test module). The `just fix` pre-commit hook ran clean.
- Working tree is clean and `master` is level with `origin/master` (the earlier 5-commit gap was resolved by the automatic rebase during the commit).

The parent epic `sase-fb` was left open.
