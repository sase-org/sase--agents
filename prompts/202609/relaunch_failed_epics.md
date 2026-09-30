- **PLAN:**
  [202609/relaunch_failed_epics.md](https://github.com/sase-org/sase--plans/blob/main/202609/relaunch_failed_epics.md)
- **AGENTS:**
  - [bbugyi200.athena.0ua--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ua.md)

Can you help me review and relaunch the 1d5, 1cx, 1cj.12, 1co, and 1ck epic beads, each
of which had an agent fail last night?

- If the failing phase in an epic actually finished its changes and closed the bead OR
  it didn't close the bead, we should be able to just run the `sase bead work <epic> -Y`
  command to relaunch that epic.
- If the failing phase closed its bead before it should have, however, you should
  re-open that bead before running the `sase bead work <epic> -Y` command to relaunch
  the epic.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
