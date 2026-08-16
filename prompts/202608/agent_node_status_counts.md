- **PLAN:**
  [202608/agent_node_status_counts.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_node_status_counts.md)
- **AGENTS:**
  - [bbugyi200.athena.046--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.046.md)

We seem to be showing agent status counts on agent families, which is something we
should never do since we should only count agent nodes on this tab. For example, the
`[U1]` agent status counts in #sshot shouldn't be showing (and agent shells that are not
agent nodes, but agent shell nodes, should not have unread indicators). Can you help me
fix this?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
