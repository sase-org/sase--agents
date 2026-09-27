- **PLAN:**
  [202609/agents_group_fold_repaint.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_group_fold_repaint.md)
- **AGENTS:**
  - [bbugyi200.apollo.29--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.29.md)

When I use the `H` keymap on the "Agents" tab to fold an agent group (see the
~/tmp/screenshots/20260927_070821.png screenshot for an example of what this is supposed
to look like), it seems to immediately work but it does not immediately show.

- For example, I can't select any of the nodes in that group using the `j`/`k` keymaps,
  but all of the nodes are still visible and the group appears expanded.
- One mitigation for this bug in the moment (might be useful to help figure out what's
  causing this): If I use the `L` keymap, the group is re-rendered as collapsed before
  the hints for the `L` keymap are rendered.

Can you help me diagnose the root cause of this issue and fix it? Think this through
thoroughly and create a plan using your `/sase_plan` skill. Choose and author the
appropriate tier, validate and revalidate until it passes, then submit it with
`sase plan propose` (as the skill instructs) before making any file changes.
