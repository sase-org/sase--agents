# Chat History - ace-run (05v--plan)

- **TIMESTAMP:** 2026-08-18 07:33:45 EDT
- **MODEL:** claude/opus
- **AGENT:** 05v--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-05v__plan-260818_072817.md`
- 2. --code — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-05v__code-260818_072817.md`

**Plan:** /home/bryan/.sase/plans/202608/launch_control_setting_labels.md


## Prompt

#gh:gh_sase-org__sase Can you help me improve the wording of the short descriptions used for some of
the config fields listed on the "Launch Control" panel?

- See #sshot for what this panel looks like currently.
- Let's use "default model" instead of "launch model".
- Let's use "max runners" instead of "running agents".

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/launch_control_setting_labels.md`

> # Reword two Launch Control setting labels
> Rename two scalar-setting row labels in the ACE Launch Control panel (leader `,m`):
> | Row                          | Current label    | New label       |
> | ---------------------------- | ---------------- | --------------- |
> | `llm_provider.default_model` | `launch model`   | `default model` |
> | `max_running_agents`         | `running agents` | `max runners`   |
> Both new labels are strictly better than what they replace:
> - `default model` matches the config path it edits (`llm_provider.default_model`) and
>   its own description strip ("Used when a launch has no explicit %model directive."), so
>   the row, the path shown beneath it, and the concept now share one word.

*See full plan file for details.*

