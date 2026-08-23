# Chat History - ace-run (0bm--plan)

- **TIMESTAMP:** 2026-08-23 08:15:34 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0bm--plan

**Plan:** /home/bryan/.sase/plans/202608/direct_typed_proc_launch.md


## Prompt

#gh:gh_sase-org__sase It doesn't seem like `%proc` directives are working correctly (see #sshot). See the sase-s6 epic bead for context on the `%proc` directive. Can you help me diagnose the root cause of this issue and fix it? Leave notes on the sase-s6 epic bead if appropriate (the epic lander is running now). Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/direct_typed_proc_launch.md`

> # Fix direct `%proc` / typed-unit launches
> ## Goal
> Make enabled `%proc` and `%if` directives execute through the existing typed launch
> planner and durable admission coordinator when a user submits them directly from ACE or
> `sase run`. A direct user submission is already authorized and must not create a
> `LaunchApproval`, but it must preserve the same immutable typed plan, digest, wait /
> condition semantics, native proc dispatch, and recovery contract used after an approved
> agent-initiated launch.
> Keep the disabled feature state and ordinary all-agent direct launches behaviorally
> unchanged. In particular, preserve forced-name-reuse handling, preplanned

*See full plan file for details.*

