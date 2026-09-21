- **PLAN:**
  [202609/preview_panel_dynamic_size.md](https://github.com/sase-org/sase--plans/blob/main/202609/preview_panel_dynamic_size.md)
- **AGENTS:**
  - [bbugyi200.athena.0ol--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ol.md)

Can you help me make the panel that pops up when the `K` keymap is used in the prompt
input widget use a dynamic size based on the number of lines of content that need to be
shown?

- When the contents can fit in the panel without increasing the size, we should continue
  to use the current size.
- When the contents can't fit we should make the panel larger up to some maximum, which
  is close to but not quite the size of the current screen.
- For example, if the `K` keymap is used when the `#research_swarm` xprompt swarm is
  selected, we should probably use the maximum panel size (since that xprompt swarm is
  defined in a markdown file that is almost 300 lines long).
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
