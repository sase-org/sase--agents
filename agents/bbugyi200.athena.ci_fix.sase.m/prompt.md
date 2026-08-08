#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_54c1436, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31272394473
Pinned failing commit: 54c1436
Failed jobs from the sweep:
- coverage-contexts
- test (3.12)
- test (3.13)
- test (3.14)
- visual-test

The pinned failure is on a settled commit older than the current unsettled HEAD
(25be8cc683343fb4bb0e9f2132446182339c2939). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.