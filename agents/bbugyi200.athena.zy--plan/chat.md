# Chat History - ace-run (zy--plan)

- **TIMESTAMP:** 2026-08-13 16:07:02 EDT
- **MODEL:** claude/opus
- **AGENT:** zy--plan

**Plan:** /home/bryan/.sase/plans/202608/phantom_starting_agent_rows.md


## Prompt

#gh:gh_sase-org__sase I feel like I am constantly (at least way too often) seeing `1 starting` on the agents tab (see #sshot for context). If I had to guess, I'd say that this has the same root cause as a bug that causes agent launches to take a while and for agents to jump from the `RUNNING` state to the `STARTING` state and back again repeatedly before finally launching. Can you help me confirm/deny my suspicion, diagnose the true root cause, and fix the issue?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/phantom_starting_agent_rows.md`

> # Plan: Stop workspace-claim placeholder STARTING rows from becoming phantoms
> ## Background: what the user reported
> Two symptoms, reported together with the suspicion that they share a root cause:
> 1. The Agents-tab headline almost always shows `1 starting`, with no corresponding row
>    anywhere in the panel.
> 2. Agent launches take a while, and during that window rows appear to jump between
>    `RUNNING` and `STARTING` repeatedly before finally settling.
> **The suspicion is correct.** Both symptoms come from the same defect, described below.
> Symptom 1 is fully reproduced and root-caused; symptom 2 is root-caused in the
> reconciliation code with one directly observed corroborating signal. The "launches take

*See full plan file for details.*

