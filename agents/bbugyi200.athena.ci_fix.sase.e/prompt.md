#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_09bb443, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31139025541
Pinned failing commit: 09bb443
Failed jobs from the sweep:
- lint
- published-core-minimum-smoke

The pinned failure is on a settled commit older than the current unsettled HEAD
(0f7960d0853a7cd52721cec1361ae1c394cd0dee). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.