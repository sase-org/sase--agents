- **PLAN:**
  [202608/lazy_beads_sidecar.md](https://github.com/sase-org/sase--plans/blob/main/202608/lazy_beads_sidecar.md)
- **AGENTS:**
  - [bbugyi200.athena.0dq--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0dq.md)

We currently auto-clone the beads sidecar repo by default. This is no longer necessary,
however, since we should now do this automatically when a `sase bead` command is run
that requires the beads repo (which is likely most of them), right? Can you help me
verify my claims and then make sase workspace initialization faster by (if I'm right and
this won't break anything) no longer auto-cloning the beads sidecar repo?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
