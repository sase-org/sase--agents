# Chat History - ace-run (0d7--plan)

- **TIMESTAMP:** 2026-08-25 07:02:06 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0d7--plan

**Plan:** /home/bryan/.sase/plans/202608/community_plugin_github_owners.md


## Prompt

#gh:gh_sase-org__sase Can you help me start always showing the GitHub organization for community plugins shown on the "Plugins" sub-tab of the "Updates" tab of the "SASE Admin Center" panel? For example, in #sshot, we should show `bbugyi200/bugyi-chops` instead of just `bugyi-chops`. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/community_plugin_github_owners.md`

> # Plan: Show GitHub owners for community plugins
> ## Current behavior and constraints
> - `PluginCatalogEntry` already carries the GitHub `owner`, repository `repo`, and
>   canonical `full_name`; the GitHub source normalizes `full_name` to `owner/repo`, and
>   the plugin detail panel already renders it.
> - The Updates > Plugins list loses that ownership context because
>   `PluginsBrowserRenderingMixin._row_text()` always renders the short `entry.name`.
> - The list's precomputed filter haystack omits `owner` and `full_name`, so an owner
>   shown in a row would otherwise not be searchable.
> - Grouping, sorting, option IDs, session bookmarks, lookup maps, marks, and plugin

*See full plan file for details.*

