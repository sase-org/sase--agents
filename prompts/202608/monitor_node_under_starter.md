- **PLAN:**
  [202608/monitor_node_under_starter.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_node_under_starter.md)
- **AGENTS:**
  - [bbugyi200.athena.04l--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04l.md)

Sometimes, when sase agents run monitors, no monitor node appears under that agent
family (see #sshot for an example of this issue).

- Note that this does work perfectly sometimes so there seems to be some kind of
  inconsistency here.
- We should be showing exactly one monitor node (with an orange gear icon instead of an
  agent icon) per monitor that is run in an agent family.
- For example, in the screenshot, the running monitor that the `sase-ns.6.6.6.1--2`
  agent started should be showing under the `sase-ns.6.6.6.1--2` agent node and the
  `sase-ns.6.6.6.1--2` agent node should not have the little gear with `1` next to it
  (though that should stay in the agent clan node).

Can you help me fix this? Think this through thoroughly and create a plan using your
`/sase_plan` skill. Choose and author the appropriate tier, validate and revalidate
until it passes, then submit it with `sase plan propose` (as the skill instructs) before
making any file changes.
