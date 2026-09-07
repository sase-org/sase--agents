#gh:gh_sase-org__sase Can you help me add a new `_` keymap to the "Agents" tab in the TUI that works
a lot like the `-` keymap on that tab except that it applies to all agent tribe panels
at once?

- If any agent drive panels have expanded nodes, then the behavior of this keymap should
  be to collapse all expanded nodes. Otherwise we should expand all previously collapsed
  nodes in all agent tribe panels as defined by the expand/collapse history.
- Make sure this new keymap works reliably regardless of which agent tribe panel / node
  is selected.

#plan