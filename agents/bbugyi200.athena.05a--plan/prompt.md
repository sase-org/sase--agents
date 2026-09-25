#gh:gh_sase-org__sase Can you help me add support for line numbers to sase's pager?

- These line numbers should be visible for all targets supported by sase's pager not
  just files.
- We should also add support for the new `;` / `:` keymaps, which both trigger the same
  prompt for a line number to jump to.
- Make sure that the line number prompt is visually distinct and easy to recognize at a
  glance but also hides as little of the sase pager's contents as possible.
- Also make sure the line number prompt makes it clear what valid range of line numbers
  the user can choose from (`1-<N>` where `<N>` is the number of lines in the target we
  are currently viewing).
- #beau

#plan %m:@xlarge