#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_9591b4e, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31311677796
Pinned failing commit: 9591b4e
Failed jobs from the sweep:
- Build and deploy docs

The pinned failure is on a settled commit older than the current unsettled HEAD
(fcc9be44f2cf5ea8b5a23ab505d50f94a508f970). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.