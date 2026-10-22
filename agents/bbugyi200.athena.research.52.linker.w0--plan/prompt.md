#gh:gh_sase-org__sase I want to make it much clearer whether or not a user can scroll down to see the
entirety of the currently focused sase agent deck (which they can only do when the cards
are not split out to sub-tabs). Can you help me implement this?

- I was thinking that we could achieve this by only showing card sub-tabs when we
  actually have split out sub-tabs (i.e. when the user has to use the `<ctrl+j/k>`
  keymaps to view other cards in the current deck).
- We could also start showing a bright and clearly visible set of badges that indicate
  the view.
- As a part of this change, I was also thinking that we stop showing "auto" and "fixed"
  and start representing this state using a little lock icon instead?
- Think hard about what the best possible UX is here (I might have gotten a few things
  wrong).
- Review the deck_scroll_scope_tabs_and_layout_lock.md file in the research sidecar repo for context and inspiration
  before planning. I agree with all of the requirements recommended in that research
  file (but keep in mind that you are responsible for planning and splitting up this
  work appropriately).
- #beau 

#plan %m:@xlarge %w:research.52.linker