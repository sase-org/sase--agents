#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_b5872ca, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31130782239
Pinned failing commit: b5872ca
Failed jobs from the sweep:
- coverage-contexts
- test (3.13)

The pinned failure is on a settled commit older than the current unsettled HEAD
(5e6a94a3890d192dca6091d2165783381c8348e3). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.