# Chat History - ace-run (nk--plan)

- **TIMESTAMP:** 2026-07-28 17:46:07 EDT
- **MODEL:** claude/opus
- **AGENT:** nk--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-nk__plan-260728_173904.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-nk__code-260728_173904.md`

**Plan:** /home/bryan/.sase/plans/202607/queued_status_for_all_runner_slot_waits.md


## Prompt

#gh:gh_sase-org__sase I thought we got rid of this use for `WAITING` in favor of the new `QUEUED` status, right? See #sshot for context. Can you help me fix this so we always use `QUEUED` when agents are waiting because of the configured maximum allowed number of running agents? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/queued_status_for_all_runner_slot_waits.md`

> # Plan: Use QUEUED for every runner-slot admission wait
> ## Problem
> Agents parked at the runner-slot admission gate still render `WAITING` whenever their threshold came from an authored
> `%wait(runners=N)` directive. Only _implicit_ global-cap waiters are promoted to `QUEUED`.
> The result is a self-contradicting Agents tab: the detail panel shows a four-entry `QUEUE` ladder (`#1 audit_bugs… ≤0`,
> `#2 audit_improvements… ≤0`, `#3 chop.refresh_docs… ≤0`, `#4 toobig-0t.split_file… ≤3 p20`), while all four of those
> same rows render `(WAITING ▶4→0)` / `(WAITING ▶4→3 p20)` in the list, and the header capacity chip counts zero queued
> agents. The selected agent's `Wait:` block shows `[agents] … ✓` — its only authored dependency is already satisfied —
> and `[runners] ≤ 3 · 4 runners still running · queue #4 of 4`. It is unambiguously sitting in the admission queue, yet
> it is labeled `WAITING`.

*See full plan file for details.*

