#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_519cd73, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/30853820388
Pinned failing commit: 519cd73f2d48c5532219eb47b3f31f8e97a63773
Failed jobs from the sweep:
- test (3.12)
- test (3.13)
- test (3.14)
- visual-test


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.