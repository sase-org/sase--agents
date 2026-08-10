- **PLAN:**
  [202608/stitch_create_migration.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_create_migration.md)
- **AGENTS:**
  - [bbugyi200.athena.xq--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.xq.md)

We recently migrated the the `sase vcs` command to `sase stitch` (see the sase-j9 epic
bead for context). Can you now help me migrate the `sase commit` command to a new
`sase stitch create` command? You'll need to update the /sase_git_commit skill but don't
rename it or change any more of its contents than necessary (I've got plans to do that
later). Initialize that skill change when you're done by running the appropriate
command.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
