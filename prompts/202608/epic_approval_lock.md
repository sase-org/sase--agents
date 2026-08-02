- **PLAN:**
  [202608/epic_approval_lock.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_approval_lock.md)
- **AGENTS:**
  - [bbugyi200.athena.rz--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.rz.md#member-plan)

It seems like it's currently impossible to approve multiple epics at the same time. At the very least it's unreliable
because we seem to use the same clones/workspaces of the sidecar repos for every epic approval. Can you help me fix this
by using lockfiles to ensure that only one epic approval attempts to run at a time (all others should wait for the
lock)? See #sshot for an example of the type of failure I am trying to fix.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs) before making
any file changes.
