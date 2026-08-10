#gh:gh_sase-org__sase We recently migrated logic specific to the agent tribe panel from the `Z`
keymap to a new `=` keymap (see the sase-j2 epic bead for context). Can you help me do
something similar with the `H` keymap's functionality?

- The `H` keymap currently collapses any agent clan / agent lane that is expanded in
  that panel when an agent tribe panel is selected.
- Let's migrate that functionality to a new `-` keymap that works even when an agent
  tribe panel is not selected.
- Also, let's add some smarts to this new `-` keymap that allows it to reverse its
  operation (i.e. expand the entries it last collapseed in this agent tribe panel) when
  there are no entries currently expanded (so there is nothing to collapse).
- Finally, let's add a brand new functionality for the `H` keymap when an agent tribe
  panel is selected. Namely, let's do something very similar to what the `L` keymap does
  in this case, but collapse the selected entry instead of expanding it.
- #beau

#plan #m_opus