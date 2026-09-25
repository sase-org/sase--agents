#gh:gh_sase-org__sase Can you help me start always showing a confirmation (confirmed by pressing
`<enter>`) when the `<enter>` keymap is used in the prompt input widget?

- We already do this when multiple prompt input widgets are shown, but we should start
  doing it when there is only one prompt input widget too.
- The `<ctrl+g><enter>` and `g<enter>` keymaps should still be able to be used to submit
  the prompt / launch the agent immediately.
- This behavior should be configurable via a new sase config field (i.e. users should be
  able to turn this off so `<enter>` immediately submits the prompt).
- #beau

#plan