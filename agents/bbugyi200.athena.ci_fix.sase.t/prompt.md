#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_8658abe, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31368571903
Pinned failing commit: 8658abee6a733ddadd7b4b5bb01225ec66c8300d
Failed jobs from the sweep:
- coverage-contexts
- lint
- published-core-minimum-smoke
- sync-release-metadata
- visual-test


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.