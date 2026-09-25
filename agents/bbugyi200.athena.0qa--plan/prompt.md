#gh:gh_sase-org__sase We recently added a sticky footer below the agent metadata panel (see the sase-16y
epic bead for context), but the agent that implemented this misunderstood me. Namely,
the agent metadata panel sections that currently contain "jump targets" (i.e. the
listings of the nodes that are targeted by the numeric keymaps) were supposed to be
MOVED to the new sticky footer. The collapsed state of this sticky footer looks good
now, but the uncollapsed state should show the same contents that are currently shown in
the agent metadata panel for these jump targets. Can you help me fix this?

#plan %m:@xlarge