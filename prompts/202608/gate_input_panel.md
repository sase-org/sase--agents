- **PLAN:**
  [202608/gate_input_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_panel.md)
- **AGENTS:**
  - [bbugyi200.athena.06q--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06q.md)

Sase gate input selection in the TUI is buggy and not intuitive. Can you help me fix
this?

- All of the inputs are currently grouped at the bottom of the left pane. This makes
  them have a very limited width and it's not clear which inputs are associated with
  which gate options.
- Let's stop showing those inputs in the left pane at all. Instead when an option is
  selected, a new panel should pop up containing all of the input components associated
  with the selected option.
- The user should be able to navigate to the next / previous input component using the
  `<tab>` / `<shift+tab>` keymaps.
- Make sure this panel is large enough that it is unlikely that input text needs to be
  wrapped.
- Also, any freeform input text boxes should support the keymaps and insert/normal modes
  that are supported by prompt input widgets. I think we have some shared
  interface/library for this.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
