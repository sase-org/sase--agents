#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_cac21c8, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31302380041
Pinned failing commit: cac21c8
Failed jobs from the sweep:
- lint
- published-core-minimum-smoke

The pinned failure is on a settled commit older than the current unsettled HEAD
(4a855032ff96612934d810a9ac0fed463d2f7448). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.