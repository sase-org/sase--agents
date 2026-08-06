#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_01398f5, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31057603899
Pinned failing commit: 01398f5afc1061812388696daf82c78441665987
Failed jobs from the sweep:
- lint
- perf-floors
- published-core-minimum-smoke
- test (3.12)
- test (3.13)
- test (3.14)


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.