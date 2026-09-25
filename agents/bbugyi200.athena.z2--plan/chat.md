# Chat History - ace-run (z2--plan)

- **TIMESTAMP:** 2026-08-13 07:31:53 EDT
- **MODEL:** claude/opus
- **AGENT:** z2--plan

**Plan:** /home/bryan/.sase/plans/202608/tribe_description_hint.md


## Prompt

#gh:gh_sase-org__sase Can you help me stop showing the description warning in the agent metadata panel when an agent tribe panel that doesn't have a description set? For example, in #sshot, the `not set · add ace.tribes.monitor-smoke.description` text should not be shown. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/tribe_description_hint.md`

> # Drop the "description not set" hint from the selected tribe panel header
> ## Problem
> When a tribe panel is selected in the ACE Agents tab, the `TRIBE` metadata header always
> ends with an unlabeled description row. When the tribe has no configured
> `ace.tribes.<name>.description`, that row renders a nag instead:
> ```
> not set · add ace.tribes.monitor-smoke.description
> ```
> This fires for every ad-hoc tribe an xprompt assigns with `%tribe:` — for example the
> `monitor-smoke` tribe in the reported screenshot — even though such tribes are never

*See full plan file for details.*

