#gh:gh_sase-org__sase #fork:sase-ri.land.w2.f2 Can you now help me add a new "Features" sub-tab to
the "Config" tab of the "SASE Admin Center" panel?

- This panel should allow the user to view/enable/disable sase's feature flags.
- Enabling/disabling feature flags from this tab should be persisted (e.g. so the same
  features are enabled/disabled when the user restarts their machine) somehow without
  altering the user's main sase configuration files. Think hard about the best way to do
  this.
- Enabling/disabling a sase feature flag should result in the TUI and AXE being
  restarted (use existing shared logic for this). Make sure the user is made aware of
  this somehow.
- #beau

#plan