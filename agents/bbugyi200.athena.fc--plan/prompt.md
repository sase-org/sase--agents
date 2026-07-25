#gh:gh_sase-org__sase The `H` keymap currently expands the currently selected agent tribe
panel and collapses every other tribe panel. Can you help me start remembering
whether the expansion state of all agent tribe panels (including the current
one, which the `H` keymap may or may not have expanded) when this keymap is used
so we can revert to that state if `H` is pressed again?

- This is meant to serve as a way to undo the `H` keymap's side effects, but
  should only be active until the next time the user changes the expansion state
  of another panel except for the one that was selected when `H` was last
  pressed (i.e. the user can expand the current agent tribe panel as much as
  they want and still use `H` to revert to the saved expansion state, but if
  they expand any other panel, we drop that old expansion state and pressing `H`
  will trigger its normal/current behavior).
- While we are in the state where the `H` keymap can be used to undo its last
  operation, make sure we visually mark the agent tribe panels that are in an
  expansion state that differs from the one they would have if the user were to
  press `H` while any agent tribe panel is selected (otherwise, `H` might have
  different behavior--e.g. folding an agent group within an agent tribe panel).
- #beau

#plan #m_fable