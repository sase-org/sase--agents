# Chat History - ace-run (0ap--plan)

- **TIMESTAMP:** 2026-08-22 12:44:13 UTC
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0ap--plan

**Plan:** /home/bryan/.sase/plans/202608/family_shell_roster.md


## Prompt

#gh:gh_sase-org__sase Can you help me rename the `FAMILY MEMBERS` section (in the agent metadata panel when an agent family is selected) to `FAMILY SHELLS` and start displaying family monitors appropriately in that section? Make sure monitor shells in the selected agent family also get an appropriate numeric keymap assigned to them.

I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/family_shell_roster.md`

> # Plan: Family shell roster with monitor navigation
> ## Outcome
> When a family container is selected in ACE's Agents tab, its metadata panel will show
> `FAMILY SHELLS`, not `FAMILY MEMBERS`. The roster will contain every concrete shell in
> causal execution order: LLM-backed agent shells and proc-backed monitor shells. Each
> visible row will receive the same zero-based numeric chip that selects it, including a
> monitor nested beneath the shell that started it. Selecting an individual family shell
> will continue to show the other shells in that family, under the same terminology.
> The presentation should make shell kinds legible at a glance. Agent rows keep their role
> and model treatment. Monitor rows use the monitor gear vocabulary, their effective

*See full plan file for details.*

