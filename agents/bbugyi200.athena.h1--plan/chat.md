# Chat History - ace-run (h1--plan)

- **TIMESTAMP:** 2026-07-21 09:23:30 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** h1--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-h1__plan-260721_091656.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260721_091656.md`

**Plan:** /home/bryan/.sase/plans/202607/warn_custom_builtin_aliases.md


## Prompt

#gh:gh_sase-org__sase When loading the "Models" panel in the TUI, can we start showing a warning message / indicator when the user has defined a custom alias that overrides a builtin alias? Advice the user that they should override the model aliases value using the `llm_provider.model_aliases.builtin` config field instead of `llm_provider.model_aliases.custom`. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/warn_custom_builtin_aliases.md`

> # Plan: Warn when custom model aliases shadow builtin aliases
> ## Context and intent
> Model alias resolution deliberately merges `model_aliases.custom` over `model_aliases.builtin`. The existing doctor
> check reports a builtin alias name placed in the custom map, but the Models panel currently presents the winning value
> as an ordinary configured alias. This makes an effective but misplaced override easy to miss, especially for `coder` and
> phase-worker aliases hidden inside collapsed builtin buckets.
> Keep the change presentation-only. Do not alter merge precedence, schema validation, alias resolution, persistent edit
> behavior, or the user's config. The warning should cover valid custom entries whose alias name is already classified as
> a builtin (`default`, a role alias, or a registered `<provider>_coder` alias). Legitimate user-defined aliases in
> `custom`, and ordinary builtin overrides already stored in `builtin`, must remain calm. Other doctor-only migration

*See full plan file for details.*

