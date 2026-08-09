- **PLAN:**
  [202608/new_task_dup_search.md](https://github.com/sase-org/sase--plans/blob/main/202608/new_task_dup_search.md)
- **AGENTS:**
  - [bbugyi200.athena.wb--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.wb.md)

I want to make sure that sase agents that use the /sase_new_task skill do not spend too
much unnecessary time searching for duplicate task beads. Can you help me make it so we
instruct them (via this skill's instructions) to use the `sase bead search` command when
searching for duplicate sase task beads? They should still use the `sase bead list`
command to check for related, in-progress epics. Make sure the instructions for this
skill are useful but concise. Remember that every token added to context either helps or
hurts us.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
