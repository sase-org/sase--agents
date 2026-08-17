- **PLAN:**
  [202608/procs_tab_monitor_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_tab_monitor_support.md)
- **AGENTS:**
  - [bbugyi200.athena.04g--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04g.md)

Can you help me add much better support for sase monitors to the "Procs" tab of the
"SASE Admin Center" panel?

- Start marking any monitor rows on this tab with the orange gear we use for monitors,
  to make it clear that this proc is associated with an agent family.
- Add support for streaming the live output of monitors to this tab, just like we do in
  the agent metadata panel for monitors.
- Start showing how many non-monitor procs / monitor procs are running via the blue and
  orange gears (with counts next to them) at the top of this tab.
- Start showing the name of the sase agent associated with the monitor and add a new
  `<enter>` keymap that allows the user to jump directly to that agent on the agents
  tab.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
