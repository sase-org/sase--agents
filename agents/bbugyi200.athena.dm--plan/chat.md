# Chat History - ace-run (dm--plan)

- **TIMESTAMP:** 2026-07-18 14:09:23 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** dm--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-dm__plan-260718_140024.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260718_140024.md`

**Plan:** /home/bryan/.sase/plans/202607/agents_status_recency_sort.md


## Prompt

#gh:gh_sase-org__sase Can you help me fix change the way that agents/agent families (just called "agents" from this point forward) are sorted when shown in the Agents tab? See #sshot for context / how this looks now. We should start sorting running agents at the top with the most recently launched agents listed first. After that we should list any done agents or complete agents and then after that we should list any agents that are waiting. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/agents_status_recency_sort.md`

> # Plan: Agents status and launch-recency ordering
> ## Context and scope
> The Agents tab already receives its flat agent list with top-level rows ordered by descending `start_time`, but
> `BY_STATUS` rebuilds that list with a fixed status-bucket order and structural name keys ahead of any time key. This is
> why the rendered tree can put Waiting before Done and can order running singleton agents and agent-family groups by
> shape/name rather than launch recency.
> This tale changes only the Agents tab's `BY_STATUS` presentation. Keep the shared status classification intact:
> successful terminal states such as `DONE`, `PLAN DONE`, `TALE DONE`, and `EPIC CREATED` continue to map to the existing
> `Done` bucket; `STANDARD`, `BY_DATE`, integration/API status ordering, filter semantics, and the intentionally hidden
> `Starting` rows remain unchanged.

*See full plan file for details.*

