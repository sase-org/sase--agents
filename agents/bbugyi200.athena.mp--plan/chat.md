# Chat History - ace-run (mp--plan)

- **TIMESTAMP:** 2026-07-28 06:24:38 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** mp--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-mp__plan-260728_061539.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-mp__code-260728_061539.md`

**Plan:** /home/bryan/.sase/plans/202607/commits_project_filter.md


## Prompt

#gh:gh_sase-org__sase Can you help me add first-class support for project filters to the
"Commits" sub-tab of the "Artifacts" tab?

- We should add a new `project:<project>` filter
- When the user uses the `p` keymap on that page to filter projects, the new
  `project:<project>` filter should be added to the current filter query.
- Remove other indications of what project we are currently filtering for (the
  `project:<project>` in the filter bar should be the user's only indication).
- Make sure that we pre-load the filter bar query appropriately (i.e. if we
  automatically filter by the current project, insert `project:<project>` in the
  filter bar when loading the commits tab).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/commits_project_filter.md`

> # First-class project filters for Artifacts Commits
> ## Goal
> Make the persistent Commits query the sole visible and authoritative representation of project filtering:
> - add a singular, non-negatable `project:<project>` facet to the Commits query language;
> - make the Commits project picker replace that facet while preserving every other committed filter, and make its “All
>   projects” choice remove the facet;
> - ensure every automatically selected current/explicit project is present in the query before the first Commits
>   collection, while an absent `project:` facet means a true all-project collection;
> - remove the separate Commits scope label and any other persistent project-scope presentation so the filter row is the
>   only project-filter indicator.

*See full plan file for details.*

