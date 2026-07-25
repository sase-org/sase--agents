# Chat History - ace-run (6d--plan)

- **TIMESTAMP:** 2026-07-11 19:50:27 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 6d--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-6d__plan-260711_193746.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260711_193746.md`

**Plan:** /home/bryan/.sase/plans/202607/model_directive_alias_overrides.md


## Prompt

#gh:gh_sase-org__sase Can you help me add support for keyword arguments to the model directive that allow the user to override specific model aliases for the agent family that is launched by this prompt? For example I should be able to use `%m(opus, coder=sonnet)` to launch an agent that will use the Claude Sonnet model for any agents that specify the `@coder` model alias. Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/model_directive_alias_overrides.md`

> # Plan: Keyword-Argument Alias Overrides on the `%model` Directive
> ## Problem
> Model aliases (`@coder`, `@phase_worker`, `@epic_creator`, custom aliases, …) are resolved from machine-global
> configuration (`llm_provider.model_aliases` in sase.yml, plus the machine-global temporary-override file
> `~/.sase/llm_override.json`). There is no way to pin an alias for a _single agent family_ at launch time. If a user
> wants this particular plan's coder follow-up to run on Sonnet while everything else keeps the configured coder model,
> they must either edit config, set a machine-global temporary override (which affects all concurrent launches), or wait
> for the plan-approval modal and pick a model manually.
> ## Feature
> Extend the `%model` / `%m` directive's paren form with keyword arguments that override specific model aliases **for the

*See full plan file for details.*

