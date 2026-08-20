- **PLAN:**
  [202608/wait_dependency_status_counts.md](https://github.com/sase-org/sase--plans/blob/main/202608/wait_dependency_status_counts.md)
- **AGENTS:**
  - [bbugyi200.athena.08l--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08l.md)

Agents with a `WAITING` status show a `Wait:` field at the top of the agent metadata
panel when selected that includes the `[agents]` and `[beads]` lines. Each agent/bead
that the agent is waiting on has a nice icon next to it (indicating the status of that
agent). For unkonwn agents, we use a `?` icon, which also gets shown in the node
corresponding to the agent that is waiting for the unknown agent. This is the only
status (unknown) that currently gets shown in the agent node (meaning that the user has
to select the waiting agent to see all other statuses). Can you help add similar
functionality to agent nodes for other statuses by adding the other supported icons to
that node with counts corresponding to the number of agents/beads associated with that
status?

I want you to lead the design on this one. Make sure you design this feature so it is
intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly
and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.
