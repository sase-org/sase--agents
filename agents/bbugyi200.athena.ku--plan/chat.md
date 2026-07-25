# Chat History - ace-run (ku--plan)

- **TIMESTAMP:** 2026-07-25 11:44:59 EDT
- **MODEL:** claude/opus
- **AGENT:** ku--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-ku__plan-260725_110900.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-ku__code-260725_110900.md`

**Plan:** /home/bryan/.sase/plans/202607/queued_agent_status.md


## Prompt

#gh:gh_sase-org__sase For agents that are queued, I'd like to start using a new `QUEUED` agent status that replaces the current `WAITING` status that we use for queued agents. This better matches the agent status counts that we use. For example, in #sshot, we should replace `WAITING ▶10/10` with `QUEUED`. Make sure we give `QUEUED` a distinct agent status color. I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/queued_agent_status.md`

> # Plan: A dedicated QUEUED agent status for runner-slot waiters
> ## Context
> ACE already counts queued agents separately from waiting ones. The Agents header reads
> `71 [10/10 running · 1 queued · 19 waiting · 41 done]`, tribe and clan chips render `[Q1 W1]`, and
> `RunnerCapacitySnapshot.global_cap_queue_count` feeds the runner-limit indicator. All of that is derived from
> `agent_is_globally_queued`.
> The row itself contradicts those counts. A queued agent still renders `WAITING ▶10/10` in amethyst, identical in kind to
> an agent blocked on a dependency, a bead, or a time floor. The two are operationally opposite: a dependency wait may
> never resolve and can warrant intervention, while a queued agent is fully unblocked and will start on its own the moment
> capacity frees. Reading the list, there is no way to tell them apart without decoding a dim glyph suffix.

*See full plan file for details.*

