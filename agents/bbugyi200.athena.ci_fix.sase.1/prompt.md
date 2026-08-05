#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_7765a07, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/30653591161
Pinned failing commit: 7765a07
Failed jobs from the sweep:
- perf-floors
- published-core-minimum-smoke
- visual-test

The pinned failure is on a settled commit older than the current unsettled HEAD
(7404e4ab1bb2c1e8f147651a0ae3bce9ade859c2). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.