# Chat History - ace-run (36--plan)

- **TIMESTAMP:** 2026-07-08 21:53:10 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** 36--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-36__plan-260708_215007.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260708_215007.md`

**Plan:** /home/bryan/.sase/plans/202607/plugin_topic_double_dash.md


## Prompt

#gh:gh_sase-org__sase We currently identify sase plugins by looking for the sase-plugin GitHub repo label. Can you help me change that so we look for sase--plugin instead? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/plugin_topic_double_dash.md`

> # Plan: Switch the Plugin Catalog Topic to `sase--plugin`
> ## Problem & Product Context
> SASE currently discovers plugins by querying GitHub repositories with the canonical repository topic `sase-plugin`:
> ```text
> gh api --paginate -X GET "search/repositories?q=topic:sase-plugin&per_page=100"
> ```
> The desired canonical marker is now `sase--plugin`. The implementation should make SASE look for that new topic
> everywhere the plugin catalog is discovered or explained, without introducing a compatibility mode that keeps accepting
> the old topic. A repository should appear in the catalog only when GitHub returns it for `topic:sase--plugin`.
> The key implementation detail is that this is not just a string in the `gh` command. The catalog cache stores the query

*See full plan file for details.*

