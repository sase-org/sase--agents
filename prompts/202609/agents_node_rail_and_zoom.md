- **PLAN:**
  [202609/agents_node_rail_and_zoom.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md)
- **AGENTS:**
  - [bbugyi200.apollo.2h--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2h.md)

We currently support collapsing the nav sidebar on the "Agents" tab via the `<ctrl+s>`
keymap.

- We also support zooming in on a single deck using the `Z` keymap, in which case the
  sidebar is also collapsed.
- When the sidebar is collapsed, it is completely invisible currently.
- This is the correct behavior when zoomed, but should not be the default format used
  when collapsing the sidebar using the `<ctrl+s>` keymap.
- Instead, every tribe, agent group (e.g. "Running"), and node should be represented
  still, just in a collapsed, fixed width state.
- I'm thinking we can use some of the icons we already support (and maybe add a few more
  if needed--for example, I'm not sure if every type of agent group has a corresponding
  icon) to accomplish this, but you should decide. Think hard about what the best UX for
  this is.
- As a part of this change, let's make it clearer (in a visually appealing way) when a
  deck is zoomed (so the user can't mistakenly think the sidebar is just collapsed).
- Review the agents_sidebar_node_rail_and_zoom.md file in the research sidecar repo for
  context and inspiration before planning.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Can you help me implement this? Think this through thoroughly and create a plan using
your `/sase_plan` skill. Choose and author the appropriate tier, validate and revalidate
until it passes, then submit it with `sase plan propose` (as the skill instructs) before
making any file changes.
