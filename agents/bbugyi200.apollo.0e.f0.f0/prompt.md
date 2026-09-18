#gh:gh_sase-org__sase #fork:0e.f0 Can you now help me add a new layout option that only shows the
files/LLM Calls panel (no agent metadata panel)?

- We should migrate the `0` (only show the agent metadata panel) key to `[` and add a
  new `]` key for this new layout.
- These two full-screen layouts should not be a part of the layout cycle that the
  `p`/`P` keys use, but we should allow those keys to be used when one of the fullscreen
  layouts is active, in which case we should switch to the 50/50 layout.

#plan