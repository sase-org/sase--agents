#gh:gh_sase-org__sase Agents with a `WAITING` status show a `Wait:` field at the top of the agent
metadata panel when selected that includes the `[agents]` and `[beads]` lines. Each
agent/bead that the agent is waiting on has a nice icon next to it (indicating the
status of that agent). For unkonwn agents, we use a `?` icon, which also gets shown in
the node corresponding to the agent that is waiting for the unknown agent. This is the
only status (unknown) that currently gets shown in the agent node (meaning that the user
has to select the waiting agent to see all other statuses). Can you help add similar
functionality to agent nodes for other statuses by adding the other supported icons to
that node with counts corresponding to the number of agents/beads associated with that
status?

#beau #plan