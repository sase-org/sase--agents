#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_b0e10d1, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31138915523
Pinned failing commit: b0e10d1
Failed jobs from the sweep:
- lint
- published-core-minimum-smoke
- test (3.12)

The pinned failure is on a settled commit older than the current unsettled HEAD
(09bb443ea4206edf188b54042713cf561fc89f94). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.