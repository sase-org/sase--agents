- **AGENTS:**
  - [bbugyi200.athena.ci_fix.sase.k](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ci_fix.sase.k/README.md)

#gh:sase-org/sase %id(ci_fix.sase.@, tribe=chop) %wait(runners=0)
#pr(ci_fix_sase_ed50d45, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31240705672 Pinned
failing commit: ed50d45 Failed jobs from the sweep:

- coverage-contexts
- test (3.12)
- test (3.13)
- test (3.14)

The pinned failure is on a settled commit older than the current unsettled HEAD
(ab442ed247dbf2aec27ab89095852d1efb3a7216). Re-verify these job failures against current
state before changing code.

First re-verify that this failure and commit are still current on the default branch. If
it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.
