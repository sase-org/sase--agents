#gh:gh_sase-org__sase Can you help me make the `g` / `G` / `<ctrl+d>` / `<ctrl+u>` / `<ctrl+f>` / `<ctrl+b>` keymaps work on the sub-tabs of the "Artifacts" tab (except for the "PRs" tab, which already has good navigation) to make navigating the list of entries in the left panel (i.e. commits, bugs, or plans) easier?

- `g` / `G` should jump to the first / last entry in the list, respectively.
- `<ctrl+d>` / `<ctrl+u>` should jump down / up 10 entries, respectively.
- `<ctrl+f>` / `<ctrl+b>` should jump down / up 5 entries, respectively.
- We should also add support for the special apostrophe functionality (supported elsewhere in the TUI) to these sub-tabs.

#plan