#gh:gh_sase-org__sase Can you help me add much better support for sase monitors to the "Procs" tab of
the "SASE Admin Center" panel?

- Start marking any monitor rows on this tab with the orange gear we use for monitors,
  to make it clear that this proc is associated with an agent family.
- Add support for streaming the live output of monitors to this tab, just like we do in
  the agent metadata panel for monitors.
- Start showing how many non-monitor procs / monitor procs are running via the blue and
  orange gears (with counts next to them) at the top of this tab.
- Start showing the name of the sase agent associated with the monitor and add a new
  `<enter>` keymap that allows the user to jump directly to that agent on the agents
  tab.
- #beau

#plan