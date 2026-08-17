#gh:gh_sase-org__sase Can you help me add a new "Glossary" panel triggered via the new `<ctrl+g>G` /
`gG` keymaps from the prompt input widget?

- As a part of this feature, we will add new `sase glossary add/del` commands, which
  allow the user to add/delete glossary term entries.
- This new panel should allow the user to navigate the glossary, both term-by-term and
  also by traveling through related terms.
- This panel should also allow the user to add/delete glossary terms. This functionality
  should use the same logic as the new commands we are adding (see the above bullet).
- The user should be able to use the new `p` / `P` keymaps to toggle to the
  next/previous enabled sase project. Only the currently selected project's glossary
  terms should be shown.
- #beau

#plan