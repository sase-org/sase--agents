#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_64f9383, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31301003143
Pinned failing commit: 64f9383
Failed jobs from the sweep:
- coverage-contexts
- lint
- perf-floors
- published-core-minimum-smoke
- test (3.12)
- test (3.13)
- test (3.14)
- visual-test

The pinned failure is on a settled commit older than the current unsettled HEAD
(cac21c867e301b97a59b3918fb8242cdae51c9b9). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.