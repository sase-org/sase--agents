- **PLAN:**
  [202608/restore_help_and_reverse_metadata_search.md](https://github.com/sase-org/sase--plans/blob/main/202608/restore_help_and_reverse_metadata_search.md)
- **AGENTS:**
  - [bbugyi200.athena.s5--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.s5.md#member-plan)

Can you help me get rid of the `?` keymap that searches the agent metadata panel backwards in favor of restoring this
keymap (on all tabs) for the help panel (this help panel is currently mapped to the `,?` keymap)? Add a `<ctrl+r>`
keymap that is only active during agent metadata panel search (triggered with the `/` keymap on the agents tab), which
reverses the search order, so we don't lose any functionality with this change. Think this through thoroughly and create
a plan using your `/sase_plan` skill. Choose and author the appropriate tier, validate and revalidate until it passes,
then submit it with `sase plan propose` (as the skill instructs) before making any file changes.
