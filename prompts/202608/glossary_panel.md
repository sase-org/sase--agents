- **PLAN:**
  [202608/glossary_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_panel.md)
- **AGENTS:**
  - [bbugyi200.athena.056--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.056.md)

Can you help me add a new "Glossary" panel triggered via the new `<ctrl+g>G` / `gG`
keymaps from the prompt input widget?

- As a part of this feature, we will add new `sase glossary add/del` commands, which
  allow the user to add/delete glossary term entries.
- This new panel should allow the user to navigate the glossary, both term-by-term and
  also by traveling through related terms.
- This panel should also allow the user to add/delete glossary terms. This functionality
  should use the same logic as the new commands we are adding (see the above bullet).
- The user should be able to use the new `p` / `P` keymaps to toggle to the
  next/previous enabled sase project. Only the currently selected project's glossary
  terms should be shown.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
