# Chat History - ace-run (xm--plan)

- **TIMESTAMP:** 2026-08-10 15:44:47 EDT
- **MODEL:** claude/opus
- **AGENT:** xm--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-xm__plan-260810_153141.md`
- 2. --code — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-xm__code-260810_153141.md`

**Plan:** /home/bryan/.sase/plans/202608/model_alias_provenance.md


## Prompt

#gh:gh_sase-org__sase When a model alias is used as an argument to the `%model` directive instead of an explicit model name, I would like to start surfacing that to the user in the agent metadata panel. Can you help me accomplish this by adding some indication next to the model names / provider names / effort levels that are shown via the `Model:` field's value (or values if an agent family is selected)?

I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/model_alias_provenance.md`

> # Show the model alias an agent was launched with in the `Model:` field
> ## Problem
> `%model:@medium_worker` and `%model:claude/opus` produce identical agent metadata. The
> `@` prefix is stripped in `normalize_model_directive`
> (`src/sase/xprompt/_directive_values.py:163`), the bare alias is resolved to a concrete
> `(provider, model, effort)` triple in `run_agent_directives.py:272-291`, and only that
> triple is written to `agent_meta.json`. The alias name is discarded at launch and is
> recoverable from nowhere afterwards.
> So the `Model:` field renders
> ```text

*See full plan file for details.*

