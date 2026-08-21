- **PLAN:**
  [202608/admin_center_launch.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_launch.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-ri.land.w2--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ri.land.w2.md)

Can you help me migrate the "Launch Control" panel (triggered via the `,m` keymap) to a
new "Launch" sub-tab on the "Config" tab of the "SASE Admin Center" panel (see the
sase-ri epic bead for context)? This new sub-tab should be triggered by the `,m` keymap,
which should now load the "Config" tab of the "SASE Admin Center" panel and select the
new "Launch" sub-tab.

I want you to lead the design on this one. Make sure you design this feature so it is
intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly
and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.
