- **PLAN:**
  [202608/proc_shell_selection_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/proc_shell_selection_jump.md)
- **AGENTS:**
  - [bbugyi200.athena.0bx--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bx.md)

There seems to be some kind of bug with stand-alone procs (launched with the `%proc`
directive). Namely when I have one focused in the agents tab and the TUI is
auto-refreshed, the selected node is changed (I think its the `0bh` or `0bd` sase agent
node that gets selected). Can you help me diagnose the root cause of this issue and fix
it? Think this through thoroughly and create a plan using your `/sase_plan` skill.
Choose and author the appropriate tier, validate and revalidate until it passes, then
submit it with `sase plan propose` (as the skill instructs) before making any file
changes.
