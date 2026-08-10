# Chat History - ace-run (x2--plan)

- **TIMESTAMP:** 2026-08-10 09:59:22 EDT
- **MODEL:** claude/opus
- **AGENT:** x2--plan

**Plan:** /home/bryan/.sase/plans/202608/runner_queue_capacity_order.md


## Prompt

#gh:gh_sase-org__sase We don't currently seem to respect the `%wait` directive's `runners` kwarg when
displaying the queued sase agents in the agent metadata panel's `QUEUE` section. All
sase agents with a lower configured number of max `runners` (i.e. the maximum number of
agents allowed to be running before that agent is allowed to launch) should be queued
after agents with a higher `runners` configuration (the default is 10 if agent's don't
use the `%wait` directive's `runners` kwarg). See ~/tmp/screenshots/20260810_093341.png
for an example of the issue I'm describing. Can you help me fix this?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/runner_queue_capacity_order.md`

> # Plan: Order the runner-slot queue display by admission eligibility
> ## Problem
> The ACE agent metadata panel's `QUEUE` ladder (and the `QUEUED #N/M` rank on agent rows,
> and `Queue: #N of M` in the detail header) ranks runner-slot waiters by `priority` then
> request-FIFO only. It ignores each waiter's `runners` threshold, so agents that cannot
> possibly start at the current occupancy are displayed ahead of the agents that will
> actually be admitted next.
> Observed by the user with 6 waiters and a nearly-full pool:
> ```
> ❖ QUEUE · 6 waiting · 10/10 runners

*See full plan file for details.*

