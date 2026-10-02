- **PLAN:**
  [202610/three_pane_splits.md](https://github.com/sase-org/sase--plans/blob/main/202610/three_pane_splits.md)
- **AGENTS:**
  - [bbugyi200.athena.0ve--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ve.md)

I would like to improve the "Agents" tab deck panel and the sase pager's split view
support (see the sase-1eg epic bead for context on the latter). Can you help me
implement this?

- We currently only support two views, each of which support just two panes: horizontal
  and vertical.
- I want to add a support for two additional views that each use three panes. Namely:
  - A horizontal split 3-pane view should be triggered when the `|` keymap is used if a
    horizontal split is already shown by splitting the currently focused pane
    vertically. Pressing `|` again should switch to the 3-pane view described in the
    bullet below. Alternatively, pressing `\` closes the larger horizontal pane which
    switches us to the 2-pane vertical view.
  - A vertical split 3-pane view should be triggered when the `\` keymap is used if a
    vertical split is already shown by splitting the currently focused pane
    horizontally. Pressing `\` again should switch to the 3-pane view described in the
    bullet above. Alternatively, pressing `|` closes the larger vertical pane which
    switches us to the 2-pane horizontal view.
- The `<ctrl+b>` keymap should be added that worked like the `<ctrl+f>` keymap (i.e.
  changes which pane is focused) but in the reverse direction.
- The new `<ctrl+shift+b/f>` keymaps should be added to give the user the ability to
  swap the current pane with the previous/next pane.
- A new `<ctrl+shift+d>` keymap should be added that deletes the current pane. This
  keymap should only be active when at least two panes are visible. We should still
  support switching back to a single-pane view when the `\` keymap is used but the
  2-pane horizontal view is already active or when the `|` keymap is used but the 2-pane
  vertical view is already active.
- Review the deck_and_pager_three_pane_splits.md file in the research sidecar repo for
  context and inspiration before planning. I agree with all of the recommendations made
  by that research file.
- Also, keep in mind that we may need to be careful that this work does not conflict
  with the ongoing work associated with the sase-1es epic bead (see the
  three_pane_splits_before_sase_1es.md file in the research sidecar repo for context).
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
