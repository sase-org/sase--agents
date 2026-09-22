- **PLAN:**
  [202609/agents_filter_indicator_format.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_filter_indicator_format.md)
- **AGENTS:**
  - [bbugyi200.apollo.1h.f0.f0.f0.w2.w0.w0--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1h.f0.f0.f0.w2.w0.w0.md)

  Can you help me change the format of the `filter: NOT machine:apollo  15/86` (for
  example) text indicator that is shown on the top-right of the TUI when agents are
  currently filtered on the "Agents" tab to `filter: NOT machine:apollo [15/86] (/)`? In
  other words, remove the extra space between the query and the agent counts, wrap the
  agent counts in square brackets, and show `(/)` to indicate the the `/` keymap can be
  used to change the filter.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
