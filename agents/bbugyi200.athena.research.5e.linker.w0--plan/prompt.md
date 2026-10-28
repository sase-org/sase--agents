#gh:gh_sase-org__sase There is not nearly enough transparancy about how the load is determined for the
current machine. For example, in the ~/tmp/screenshots/20261026_172751.png screenshot
you can see that there are 6 agents running (from the agent count at the top), but the
load is only at 3/8. This seems like it is probably a mistake/bug (I only see 1 agent
that is running a waiting monitor, so I would expect a load of 5 I think--I'm not sure),
but the bigger problem is that it is very unclear what error we are making right now, if
any (which nodes do not have any weight associated with them, for example).

Can you help me implement this? Review the machine_load_accounting_transparency.md file in the research sidecar
repo for context and inspiration before planning. I agree with all of the requirements
recommended in that research file (but keep in mind that you are responsible for
planning and splitting up this work appropriately).

#plan %m:@xlarge %w:research.5e.linker