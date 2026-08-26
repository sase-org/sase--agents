- **PLAN:**
  [202608/session_scoped_tab_memory.md](https://github.com/sase-org/sase--plans/blob/main/202608/session_scoped_tab_memory.md)
- **AGENTS:**
  - [bbugyi200.athena.0e8--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0e8.md)

There are several places throughout sase's TUI where we seem to remember the tab/subtab
that the user was last on in their last TUI session. We default to activating that tab
instead of activating the first tab in the list. For example, the "XPrompts" sub-tab of
the "Config" tab of the "SASE Admin Center" panel seems to always be loaded when I
activate the "Config" tab (I'm not sure if this is related but fix this too). Can you
help me fix this so sase remembers the previous focused tab/subtab for this TUI session
only?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
