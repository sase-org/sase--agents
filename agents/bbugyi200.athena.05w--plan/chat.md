# Chat History - ace-run (05w--plan)

- **TIMESTAMP:** 2026-08-18 07:54:02 EDT
- **MODEL:** claude/opus
- **AGENT:** 05w--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-05w__plan-260818_074321.md`
- 2. --code — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-05w__code-260818_074321.md`

**Plan:** /home/bryan/.sase/plans/202608/weighted_model_alias_pool_members.md


## Prompt

#gh:gh_sase-org__sase Can you help me improve our existing model alias pool syntax to add support for
specifying that a particular model should be used more than others?

- Let's implement this by allowing a positive integer to be placed before a model in a
  model alias pool string (separated by a space) to specify how that model should be
  weighted in the pool.
- For example, if the `@foobar` model alias is assigned a value of
  `claude/sonnet@xhigh | codex/gpt-5.5@xhigh | 3 grok/grok-4.6@xhigh`, then for every 5
  sase agent launches that use this model alias, 3 of them should use grok-4.6, 1 of
  them should use sonnet, and 1 of them should use gpt-5.5.
- When deciding which model to use in a model pool, we should be smart about this and
  try to distribute the load across models as evenly as possible without violating the
  specified weights.
- We shouldn't, for example, just use grok 3 times in a row for the `@foobar` model
  alias example given above. A smarter sequence of model selections for the `@foobar`
  model alias would look something like this:
  `sonnet -> grok -> codex -> grok -> grok -> sonnet -> ...`

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/weighted_model_alias_pool_members.md`

> # Weighted members in load-balanced model alias pools
> ## 1. Goal and user-visible behavior
> Today a `|` model alias value is a flat round-robin pool: every member gets an equal
> share of launches. This plan adds an optional per-member weight so one member can be
> favored over the others.
> Given:
> ```yaml
> llm_provider:
>   model_aliases:
>     custom:

*See full plan file for details.*

