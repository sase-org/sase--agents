#gh:gh_sase-org__sase #fork:hq Can you now help me add a new behavior for the `H` keymap when
an agent tribe panel is selected? Namely, let's add three behaviors and should
prioritize these behaviors in the order that they are listed:

- If any agent houses are currently expanded, we should prefer to fully collapse
  any agent houses in an agent tribe panel when `H` is pressed and that agent
  tribe panel is selected.
- If any top-level expanded groups exist in this agent tribe panel, we should
  collapse the last top-level panel group (ex: `Done` if grouping `by status` or
  `Yesterday` if grouping `by date`) in the panel that is currently expanded.
- Otherwise, we should collapse the agent tribe panel (just like the `h` keymap
  would do).

#plan