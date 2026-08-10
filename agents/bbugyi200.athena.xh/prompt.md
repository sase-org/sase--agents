#gh:gh_sase-org__sase We currently use the `Z` keymap for two functionalities on the agents tab in
the TUI:

1. Show the zoom panel when an agent clan / agent lane is selected.
2. Collapse all agent tribe panel's except for the currently selected one (or reverse
   this operation).

Can you help me make the 2nd functionality use a new `=` keymap instead? This means that
we should be able to use this functionality even when an agent tribe panel is not
selected now. Also, let's add support to agent tribe's for the zoom panel (so the `Z`
keymap works when an agent tribe panel is selected).

#plan #m_opus