#gh:sase-org/sase
%id(ci_fix.sase, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_f268b89, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/30423697479
Pinned failing commit: f268b89
Failed jobs from the sweep:
- test (3.14)

The pinned failure is on a settled commit older than the current unsettled HEAD
(6fcf3913de7dd251f3280bf6ae210beca0ecf073). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.