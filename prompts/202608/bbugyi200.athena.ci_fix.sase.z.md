- **AGENTS:**
  - [bbugyi200.athena.ci_fix.sase.z](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ci_fix.sase.z/README.md)

#gh:sase-org/sase %id(ci_fix.sase.@, tribe=chop) %wait(runners=0)
#pr(ci_fix_sase_62951ab, status=ready)

#actstat(repo=sase-org/sase)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/31575953995 Pinned
failing commit: 62951abcb4a20d3c7ad5c01190433ee91f837f9c Failed jobs from the sweep:

- Build and deploy docs
- coverage-contexts
- sync-release-metadata
- test (3.12)
- test (3.13)
- visual-test

First re-verify that this failure and commit are still current on the default branch. If
it was superseded or already fixed, leave the worktree unchanged and report that
outcome. Keep any fix narrowly scoped and run the relevant checks.
