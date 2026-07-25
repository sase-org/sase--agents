# Chat History - ace-run (2k--plan)

- **TIMESTAMP:** 2026-07-08 14:45:56 EDT
- **MODEL:** claude/opus
- **AGENT:** 2k--plan

**Plan:** /home/bryan/.sase/plans/202607/multi_agent_family_attach_inbatch_parent.md


## Prompt

#gh:gh_sase-org__sase If I attempt to use the `%n(foo, bar)` directive on the 2nd agent in a multi-agent prompt where the first agent specified `%n:foo` for its name, this fails since the "foo" sase agent doesn't exist at the time we try to launch the 2nd agent. It's important that we be able to add custom agent family members like this from multi-agent prompts. Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/multi_agent_family_attach_inbatch_parent.md`

> # Plan: Attach `%n(parent, suffix)` to an in-batch sibling named earlier in the same multi-agent prompt
> ## Problem
> In a multi-agent prompt, naming an agent in one segment and attaching a new family member to it from a later segment
> fails:
> ```text
> %n:foo Plan the change.
> ---
> %n(foo, reviewer) Review foo's plan.
> ```
> The second segment errors at launch time:

*See full plan file for details.*

