- **PLAN:**
  [202608/agents_panel_fold_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/agents_panel_fold_sweep.md)
- **AGENTS:**
  - [bbugyi200.athena.xo--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.xo.md)

We recently migrated logic specific to the agent tribe panel from the `Z` keymap to a
new `=` keymap (see the sase-j2 epic bead for context). Can you help me do something
similar with the `H` keymap's functionality?

- The `H` keymap currently collapses any agent clan / agent lane that is expanded in
  that panel when an agent tribe panel is selected.
- Let's migrate that functionality to a new `-` keymap that works even when an agent
  tribe panel is not selected.
- Also, let's add some smarts to this new `-` keymap that allows it to reverse its
  operation (i.e. expand the entries it last collapseed in this agent tribe panel) when
  there are no entries currently expanded (so there is nothing to collapse).
- Finally, let's add a brand new functionality for the `H` keymap when an agent tribe
  panel is selected. Namely, let's do something very similar to what the `L` keymap does
  in this case, but collapse the selected entry instead of expanding it.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
