- **AGENTS:**
  - [bbugyi200.athena.ci_fix.sase.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ci_fix.sase.4/README.md)

#gh:sase-org/sase %id(ci_fix.sase.@, tribe=chop) %wait(runners=0) #pr(ci_fix_sase_39ef28e, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/30771239483 Pinned failing commit: 39ef28e Failed jobs
from the sweep:

- test (3.12)
- test (3.13)

The pinned failure is on a settled commit older than the current unsettled HEAD
(fe0d71e09fc1ce0984d67df49917c8e2055c0b4b). Re-verify these job failures against current state before changing code.

First re-verify that this failure and commit are still current on the default branch. If it was superseded or already
fixed, leave the worktree unchanged and report that outcome. Keep any fix narrowly scoped and run the relevant checks.
