#gh:sase-org/sase
%id(ci_fix.sase.@, tribe=chop)
%wait(runners=0)
#pr(ci_fix_sase_fcaf211, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/30664093456
Pinned failing commit: fcaf211
Failed jobs from the sweep:
- published-core-minimum-smoke

The pinned failure is on a settled commit older than the current unsettled HEAD
(f0e1a25e6ee5be14ba7e94439610d64e261d2500). Re-verify these job failures against current state
before changing code.


First re-verify that this failure and commit are still current on the default branch.
If it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.