- **PLAN:**
  [202610/tui_restart_dependencies.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_restart_dependencies.md)
- **AGENTS:**
  - [bbugyi200.athena.0vz--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vz.md)

Sometimes when a sase agent is running a command like `just check` (or maybe all of the
time; I'm not sure) using the `sase tool` command, it will show up as a proc via the
little blue gear that is shown for background procs and if we try to update the TUI (for
an update triggered by the `,E` keymap, for example), then there is a toast that tells
us that we need to wait for that proc before the TUI can restart. Is that really
necessary? If not, use your /sase_plan skill to plan the appropriate changes. I thought
that things like `just check` could be run at the same time as a TUI restart, but maybe
I am missing something here, so make sure you verify everything yourself.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
