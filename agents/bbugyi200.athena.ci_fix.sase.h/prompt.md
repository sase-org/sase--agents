#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_c37e68f, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31180279221
Pinned failing commit: c37e68f
Failed jobs from the sweep:
- coverage-contexts
- test (3.14)

The pinned failure is on a settled commit older than the current unsettled HEAD
(57a045cfc6a7f72308d71d0ec66fb1b39f9af13f). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.