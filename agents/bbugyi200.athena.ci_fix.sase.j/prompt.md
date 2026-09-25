#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_28d40c5, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31217664032
Pinned failing commit: 28d40c5
Failed jobs from the sweep:
- coverage-contexts
- test (3.12)
- test (3.13)
- test (3.14)

The pinned failure is on a settled commit older than the current unsettled HEAD
(aaa8245df375ee96f68bbeef62c0e1d60c3e2735). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.