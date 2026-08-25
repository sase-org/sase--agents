- **PLAN:**
  [202608/artifacts_query_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)
- **AGENTS:**
  - [bbugyi200.athena.0do--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md)

A lot of the sub-tabs on the "Artifacts" tab are very slow to load results from queries
(especially the "Agent" sub-tab). We default to using a `limit:100` query filter for all
of these sub-tabs, so we should be able to optimize a bit more than we are now, right?
Can you help me make the queries on all of these sub-tabs (again, especially the "Agent"
sub-tab) MUCH faster?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
