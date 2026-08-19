#gh:gh_sase-org__sase I want to add a new memory file panel to the TUI that allows user to
view/add/modify/delete sase memory files from the TUI. Can you help me implement this?

- This panel should support filtering by project and should respect the current project
  (i.e. filter by that project by default--see how we do this on "Artifacts" sub-tabs
  for inspiration).
- This panel should be triggered by the new `<ctrl+g>m` (insert-mode) / `gm`
  (normal-mode) keymaps.
- This panel should support navigating memory files individually but should also support
  jumping to linked (via a memory file's optional `parent` frontmatter field) memory
  files.
- See how the recently added glossary panel (triggerd via the `<ctrl+g>G` / `gG`
  keymaps) works for inspiration.
- #beau

#plan