- **PLAN:**
  [202608/new_task_recent_task_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/new_task_recent_task_sweep.md)
- **AGENTS:**
  - [bbugyi200.athena.wu--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.wu.md)

We recently changed the guidance given by the /sase_new_task xprompt skill to instruct
agents to use the `sase bead search` command to find related/duplicate task beads. Can
you help me make sure this skill also instructs agents to review every sase task bead
(using the `sase bead list` command--I think this command supports filtering by create
date; if not, you should add support) that has been created in the last week before
confirming there are no duplicate/related beads? Also, make sure that this skill
explicitly instructs agents to make notes about related beads if some are found that do
not quite qualify as duplicates but that the agent who works the new task bead should be
aware of (we might already do this, but I'm not sure).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
