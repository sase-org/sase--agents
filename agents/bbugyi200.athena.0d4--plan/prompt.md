#gh:gh_sase-org__sase We recently added support for showing the currently running family shell's
runtime on that agent family's node. Can you now help me do something similar for agent
clans?

- Since multiple agent lanes can be active in a given agent clan, we should only show
  the lowest runtime among all running agent lanes in that clan.
- For example in the #sshot screenshot the currently selected agent clan should show
  `15m30s / ` before that agent clan's run time.

#plan