#gh:gh_sase-org__sase There are several locations in sase's TUI where we support the `<ctrl+k>`
keymap to load more entries into the current panel (e.g. the prompt history panel, the
model alias history panel, etc...). Can you help me update all of these locations to use
`<ctrl+j>` for this functionality instead?

- We should then re-purpose the `<ctrl+k>` keymap to undo the `<ctrl+j>` keymap's
  operation (i.e. "unload" the last N entries).
- Also, let's add support for these keymaps to each of the sub-tabs on the "Artifacts"
  tab by adding support for a `limit:<N>` query filter (some sub-tabs already support
  this) and adjusting it up (for `<ctrl+j>`) or down (for `<ctrl+k>`) when these keymaps
  are used. Make sure the `limit:<N>` filter is added to the default query used for each
  sub-tab.
- `<N>` should be configuratble (add a new sase config field for this) but should
  default to 100.

#plan %m:grok-4.6