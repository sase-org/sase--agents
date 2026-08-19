- **PLAN:**
  [202608/load_more_ctrl_j.md](https://github.com/sase-org/sase--plans/blob/main/202608/load_more_ctrl_j.md)
- **AGENTS:**
  - [bbugyi200.athena.086--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.086.md)

There are several locations in sase's TUI where we support the `<ctrl+k>` keymap to load
more entries into the current panel (e.g. the prompt history panel, the model alias
history panel, etc...). Can you help me update all of these locations to use `<ctrl+j>`
for this functionality instead?

- We should then re-purpose the `<ctrl+k>` keymap to undo the `<ctrl+j>` keymap's
  operation (i.e. "unload" the last N entries).
- Also, let's add support for these keymaps to each of the sub-tabs on the "Artifacts"
  tab by adding support for a `limit:<N>` query filter (some sub-tabs already support
  this) and adjusting it up (for `<ctrl+j>`) or down (for `<ctrl+k>`) when these keymaps
  are used. Make sure the `limit:<N>` filter is added to the default query used for each
  sub-tab.
- `<N>` should be configuratble (add a new sase config field for this) but should
  default to 100.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
