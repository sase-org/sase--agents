#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_8658abe, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31368571903
Pinned failing commit: 8658abe
Failed jobs from the sweep:
- coverage-contexts
- lint
- published-core-minimum-smoke
- sync-release-metadata
- visual-test

The pinned failure is on a settled commit older than the current unsettled HEAD
(8ed11bb80b6a218dcd49fed5529573e036bc32ca). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.