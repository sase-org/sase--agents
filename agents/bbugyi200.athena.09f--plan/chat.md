# Chat History - ace-run (09f--plan)

- **TIMESTAMP:** 2026-08-21 09:41:57 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 09f--plan

**Plan:** /home/bryan/.sase/plans/202608/soft_disabled_pool_styling.md


## Prompt

#gh:gh_sase-org__sase Can you help me stop showing "soft" to represent soft-disablement of LLM providers (see #sshot for context)? Instead, let's just make the entire provider yellow, including the checkmark icon (if we will use this model because it is the only not-disabled model provider in the model alias pool) and the X icon (if there are other models in the pool that are not soft disabled--so we will not use the soft disabled model in that model alias pool).

I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/soft_disabled_pool_styling.md`

> # Plan: Amber soft-disabled members in alias routing summaries
> ## Context and scope
> Launch Control's highlighted-alias description currently renders a soft-disabled
> selector member as an ordinary green available target followed by a yellow `soft`
> suffix. That splits one routing state across two visual signals and always leaves the
> member with a checkmark, even when round-robin routing is deliberately sparing it.
> Replace that compact pool/fallback-member treatment only. Provider-management surfaces
> (the disabled-provider title line, Provider Routing rows and descriptions, model picker,
> completion provenance, notifications, and tooltips) should retain explicit soft-disable
> wording because they do not all have a selected-member marker and must remain

*See full plan file for details.*

