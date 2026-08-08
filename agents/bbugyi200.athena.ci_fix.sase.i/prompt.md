#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_1a43f49, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31205884519
Pinned failing commit: 1a43f49
Failed jobs from the sweep:
- coverage-contexts
- perf-floors
- test (3.12)
- test (3.13)
- test (3.14)

The pinned failure is on a settled commit older than the current unsettled HEAD
(28e8ed1cebc384f1a283cf7b010c27d981b7f49d). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.