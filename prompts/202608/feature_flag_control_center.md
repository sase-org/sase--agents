- **PLAN:**
  [202608/feature_flag_control_center.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flag_control_center.md)
- **AGENTS:**
  - [bbugyi200.athena.09g--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09g.md)

Can you help me add a new "Flags" sub-tab to the "Config" tab of the "SASE Admin Center"
panel?

- This panel should allow the user to view/enable/disable sase's feature flags.
- Enabling/disabling feature flags from this tab should be persisted (e.g. so the same
  features are enabled/disabled when the user restarts their machine) somehow without
  altering the user's main sase configuration files. Think hard about the best way to do
  this.
- Enabling/disabling a sase feature flag should result in the TUI and AXE being
  restarted (use existing shared logic for this). Make sure the user is made aware of
  this somehow.
- As a part of this feature, we should add the new `sase flag enable/disable <flag>`
  commands that allow the user to enable/disable feature flags from the command-line.
  Make sure these commands share the same logic used to enable/disable flags from the
  new "Flags" sub-tab.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
