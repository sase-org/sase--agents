#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_222dd1e, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31148013407
Pinned failing commit: 222dd1e
Failed jobs from the sweep:
- published-core-minimum-smoke
- test (3.12)

The pinned failure is on a settled commit older than the current unsettled HEAD
(5b3f3494b9488719acacfa067d570fdef4d05f61). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.