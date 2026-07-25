#gh:gh_sase-org__sase #fork:hc now that I think about it I don't think this is the right approach. Can you help me make some changes?

- Let's instead start using the `h` keymap exclusively for navigating to the left, except for when an agent tribe panel is selected in which case we should continue to collapse the panel (and `H` should retain its current behavior).
- The `h` keymap should take over the behavior we just gave `H`.
- Additionally when the `h` keymap is used on an agent/agent family/agent clan that lives directly (i.e. is not contained in an agent clan/agent family) in an agent tribe panel, we should select that agent tribe panel now.
- The `H` keymap should take over for all collapsing functionality that the `h` keymap used to handle (this keymap should continue to collapse groups that are contained in agent tribe panels but this should be the lowest priority; we should prefer to collapse the selected / containing agent family / agent clan instead). 

#plan