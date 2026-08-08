#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_ab442ed, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31241179194
Pinned failing commit: ab442ed
Failed jobs from the sweep:
- coverage-contexts
- published-core-minimum-smoke
- test (3.12)
- test (3.13)
- test (3.14)

The pinned failure is on a settled commit older than the current unsettled HEAD
(c181d4c2442a47140f6465fb204decd4b7eac70d). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.