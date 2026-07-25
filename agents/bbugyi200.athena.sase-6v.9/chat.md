# Chat History - ace-run (sase-6v.9--plan)

- **TIMESTAMP:** 2026-07-18 22:19:25 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** sase-6v.9--plan

**Plan:** /home/bryan/.sase/plans/202607/statistics_project_changespec_views.md


## Prompt

#gh:gh_sase-org__sase Can you help me make sure that we track and display, on the statistics tab of the sase Admin Center panel, which projects or ChangeSpecs sase agents ran on? Also make sure that we offer several views and/or grouping strategies for projects / ChangeSpecs. I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/statistics_project_changespec_views.md`

> # Plan: Track and display agent work by project and ChangeSpec in Statistics
> ## Context
> The Admin Center Statistics tab (built by the sase-6y epic) computes all of its numbers on demand from the durable agent
> artifact index (`~/.sase/agent_artifact_index.sqlite`, table `agent_artifacts`), via the Rust `agent_stats` module in
> the `sase-core` linked repo and the thin Python facade in `src/sase/stats/`. The sase-6y plan explicitly deferred
> per-project statistics as "a natural follow-up"; this epic is that follow-up, extended to ChangeSpecs.
> What the durable data already records, verified against the live index (3,291 rows):
> - **Project attribution is complete.** `project_name` is an indexed column populated on every row.
> - **ChangeSpec attribution exists but is conflated.** `cl_name` is an indexed column (index
>   `idx_agent_artifacts_cl_name`) whose value is the launch-time ChangeSpec name — but when an agent is launched without

*See full plan file for details.*

