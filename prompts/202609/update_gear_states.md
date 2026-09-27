- **PLAN:**
  [202609/update_gear_states.md](https://github.com/sase-org/sase--plans/blob/main/202609/update_gear_states.md)
- **AGENTS:**
  - [bbugyi200.apollo.2d--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2d.md)

Can you help me improve the little green icon that is shown when a proc is running to
update sase?

- In particular, I want to add support for a yellow and red gear in the same place.
- The yellow gear should be used in cases where the update is complete but we are
  waiting to restart the TUI and sase service for some reason (a different proc that is
  specific to that TUI instance needs to complete, for example).
- The red gear should be used when the last time the user attempted to update, the
  update (or attempt to plan the update) failed for some reason.
- The red/yellow/green gears in this location are mutually exclusive (i.e. there should
  only ever be at most one gear shown in this location).
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
