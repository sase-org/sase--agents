# Chat History - ace-run (sase-g5)

- **TIMESTAMP:** 2026-08-06 10:43:50 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-g5

## Prompt

#gh:gh_sase-org__sase #commit
%id(sase-g5, bead=sase-g5)
%m:@medium_phase_worker
Can you complete the work for task bead sase-g5? The bead is already reserved for you and assigned to your
agent name: it was set to status=in_progress by the launch that started you; do not set the status by hand. Run
`sase bead show sase-g5`, read the description and notes, do the work, and close the bead with
`sase bead close sase-g5 --note "<what you verified>"`. If you discover genuinely distinct follow-up work,
do not expand this bead's scope: use `/sase_new_task` to check duplicates and active epics, then record it in the
location that skill selects.

## Response

I'll start by reading the bead.

Now let me read `prepare_workspace` — the workspace-prep pass.

Diagnosis confirmed. Now implementing the fix.

Now the guard helpers:

Now make the helper private and add tests.

Confirmed red-before / green-after. Now the full check gate:

Pre-existing on a clean tree — unrelated to my change. Let me review my diff, then file that failure as a task bead.

The fix is complete. Now filing the unrelated pre-existing test failure:

No bead needed — that failure is already fixed on `origin/master` (commit `d9c13549f`, phase sase-g4.3, which explicitly updates that fixture); my workspace checkout is ~30 min stale while carrying the newer `sase-core-rs` wheel. Closing the bead:

Done. Bead `sase-g5` is closed.

## Root cause

The actor was **`sase repo open agents`**. `repo_handler_open` → `prepare_opened_checkout` → `axe.runner_workspace.prepare_workspace` runs `git reset --hard HEAD` + `git clean -fd` + a checkout against the resolved checkout — and for the agents sidecar that checkout is `~/.sase/projects/gh_sase-org__sase/repos/agents`, a *single clone shared by all 24 workspaces* (`sase repo list` shows `agents  sidecar  24/24`).

Confirmed on the live clone: the reflog has `reset: moving to HEAD` + `checkout: moving from main to main` at 09:16:11, one second before the truncating commit `6ad0b6e2a` at 09:16:12. A second bare checkout at 09:19:44 pairs with `sase repo log --repo agents` (`last_opened_at 2026-08-06T13:19:45Z`, agent `u0`, workspace #11) — 47 opens by 44 distinct agents against that one clone.

**The interleaving:** every agents-sync mutator serializes on `<git_dir>/sase-agents-sync.lock`. `prepare_workspace` was the one actor that took no lock. agents-sync stages its whole regenerated payload in the worktree *before* committing, so `manifest.json` was dirty-tracked at that instant. `git reset --hard` rewrites a dirty tracked file by unlinking it before recreating it; `v2_manifest_io.read_owner_manifest` returns an **empty** manifest for a non-existent path, and `publication_planning.plan_hoods` seeds its entry map from that read. A targeted one-hood publication (`tv`) that read inside the unlink window republished from an empty base — the 1-hood manifest, with all 1391 hood directories still on disk.

## Fix

`src/sase/axe/runner_workspace.py:90` — `prepare_workspace` now runs its clean/checkout/sync pass inside `_agents_sidecar_sync_guard`, taking the same `sase-agents-sync.lock` when the target is the machine-shared `<sase_projects_dir>/<key>/repos/agents` clone, and returning `False` with a named diagnostic when it's busy. Everything else, including a workspace-scoped `sase/repos/agents` clone, is unaffected. This is sase-ab.1's protect-before-clean shape applied to the agents sidecar; no commits are at risk here (`reset --hard HEAD` drops none, payload is regenerated every pass), so the lock alone is sufficient.

New `tests/test_axe_runner_workspace_agents_lock.py` covers all three cases; verified red before the fix (2 of 3 fail), green after.

## Verification

`just check`: all lint gates green, 25968 passed / 1 failed. That one failure — `test_plan_display.py::test_malformed_header_block_leaves_authored_metadata_visible` — reproduces on a clean stashed tree and is already fixed on `origin/master` by `d9c13549f` (sase-g4.3), which rewrites that exact fixture; this workspace checkout predates it while carrying the newer `sase-core-rs` wheel. No bead filed for it.

I left the plan's Fix 3/Fix 4 (which aren't on master yet) untouched — those are that plan's containment/repair work, this bead was the source fix. No commit made.

Bead close is published (no unpublished-state diagnostic). Now committing.

Committed and pushed; working tree clean, branch level with `origin/master`.

**Bead `sase-g5`** — closed and published (the close re-run reported "already closed" with a new note, no unpublished-state diagnostic).

**What landed** (`625b5cac4`):

- `src/sase/axe/runner_workspace.py:90` — `prepare_workspace` now wraps its clean/checkout/sync pass in `_agents_sidecar_sync_guard`, which takes the same `<git_dir>/sase-agents-sync.lock` every agents-sync mutator holds, but only when the target is the machine-shared `<sase_projects_dir>/<key>/repos/agents` clone. When the lock is busy it returns `False` with a named stderr diagnostic. Per-workspace `sase/repos/agents` clones and all other workspaces are untouched.
- `tests/test_axe_runner_workspace_agents_lock.py` — new, covering the shared-clone-locked, lock-busy, and non-agents-workspace paths.

**Root cause:** `prepare_workspace` was the one actor mutating the shared agents clone without the sync lock. Agents-sync stages its regenerated payload in the worktree before committing, so `manifest.json` was dirty-tracked; `git reset --hard` unlinks a dirty tracked file before recreating it, `read_owner_manifest` returns an empty manifest for a missing path, and `plan_hoods` seeded from that empty base — republishing the 1-hood (`tv`) manifest while all 1391 hood directories stayed on disk. The agents-repo reflog corroborates: `reset: moving to HEAD` + `checkout: moving from main to main` at 09:16:11, one second before commit `6ad0b6e2a`.

**Verification:** the new tests were red before the fix (2 of 3) and green after. `just check` ran all lint gates green with 25968 passed / 1 failed; that failure (`test_plan_display.py::test_malformed_header_block_leaves_authored_metadata_visible`) reproduced on a clean tree and was already fixed upstream by `d9c13549f`, which is now the parent of my commit — so it is resolved in the pushed tree. The commit's own `just fix` before-hook passed.
