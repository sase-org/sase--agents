# Chat History - ace-run (d8--plan)

- **TIMESTAMP:** 2026-07-18 07:43:06 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** d8--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-d8__plan-260718_073421.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260718_073421.md`

**Plan:** /home/bryan/.sase/plans/202607/model_alias_picker_options.md


## Prompt

#gh:gh_sase-org__sase Can you help me start adding model alias options (ex: `@coder` as shown in #sshot) to the model options provided when the user edits/overrides a model alias from the "Models" panel? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/model_alias_picker_options.md`

> # Plan: Model-alias targets in the Models-panel picker
> ## Context and outcome
> The Models panel already displays every implicit and configured model alias, and the configuration layer already accepts
> alias-to-alias values such as `big_epic_lander: "@coder"`. The Edit and Override actions nevertheless open the shared
> `ModelPickerModal` with only provider-grouped concrete models. As a result, filtering for `@coder` produces “No matching
> models” and forces the user through `Custom...`, even though SASE knows the alias, its description, its chain, and its
> effective provider/model.
> Make aliases feel native in the two Models-panel picker flows. A user should be able to press `e` or `o`, see a compact
> alias section before the provider model sections, filter by `@coder` or `coder`, understand the alias’s current target,
> and select it with the same navigation and jump controls as a model. Persistent Edit stores the selected `@alias`

*See full plan file for details.*

