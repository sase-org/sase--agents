#gh:gh_sase-org__sase Can you help me add support for two-character hint values in the TUI?

- We should use `00` to start, then `01`, up to `09` and then `0a`, all the way up to `ZZ`.
- We should only use two-character hints in the TUI when we need to. For example
  we should show two-character hints when using the special apostrophe keymap if there are more than 62 agents
  shown on the agents tab. Otherwise we should continue to showing one-character
  hints.
- Let's start making the first hint shown for one-character hints `0` instead of `1`, just to be consistent.

#plan