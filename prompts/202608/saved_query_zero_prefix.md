- **PLAN:**
  [202608/saved_query_zero_prefix.md](https://github.com/sase-org/sase--plans/blob/main/202608/saved_query_zero_prefix.md)
- **AGENTS:**
  - [bbugyi200.athena.vf--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.vf.md)

Can you help me fix the saved PR / ChangeSpec query keymaps (which are mapped to
"Artifacts" sub-tabs now)?

- Let's have each numeric saved query keymap use the `0` prefix now.
- For example, after this change we would use `02` to load the 2nd saved PR query slot
  instead of `2`.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
