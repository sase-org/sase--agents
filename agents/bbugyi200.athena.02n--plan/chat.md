# Chat History - ace-run (02n--plan)

- **TIMESTAMP:** 2026-08-15 14:28:15 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 02n--plan

**Plan:** /home/bryan/.sase/plans/202608/simplify_models.md


## Prompt

#gh:gh_sase-org__sase Can you help me drastically simplify sase's builtin model aliases and improve
the "Models" panel (triggered by the `,m` keymap)?

- We should maintain the ability for users to configure their own model aliases and
  model alias buckets, but all builtin buckets should be removed and all builtin model
  aliases should be removed except for the `@<size>_worker` model aliases, which
  currently live in the `phase_worker` bucket but should be top-level (i.e. no bucket)
  after this change.
- These `@<size>_worker` model aliases should be renamed to just `@<size>` (for example,
  the `@medium_worker` model alias should be renamed to `@medium`).
- These `@<size>` model aliases should have default values equal to the value currently
  used by the `@smart` / `@cheap` model alias variant that the corresponding
  `@<size>_worder` model alias is currently configured to use by default (for example,
  `@large` should have a default value of
  `claude/opus@xhigh | codex/gpt-5.6-sol@xhigh`).
- The `@default` model alias, which was never used explicitly anyway, should be removed
  in favor of using a sase config field (which should default to using `@large` for its
  value).
- Similarly, the `@epic_lander` and `@big_epic_lander` model aliases should be removed
  in favor of new sase config fields.
- Make sure that all of these config fields have their current values displayed on this
  re-designed panel somewhere (probably with the runner limit and the default effort
  level).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/simplify_models.md`

> # Simplify Built-in Models and Redesign the Models Panel
> ## Outcome
> SASE will have one small, legible built-in model vocabulary:
> | Built-in alias | Direct shipped target                                                                               |
> | -------------- | --------------------------------------------------------------------------------------------------- |
> | `@xsmall`      | `claude/sonnet@medium \| codex/gpt-5.5@medium \| grok/grok-4.6@medium \| agy/gemini-3.7-flash-high` |
> | `@small`       | `claude/sonnet@high \| codex/gpt-5.5@high \| grok/grok-4.6@high`                                    |
> | `@medium`      | `codex/gpt-5.5@xhigh \| claude/sonnet@xhigh \| grok/grok-4.6@xhigh`                                 |
> | `@large`       | `claude/opus@xhigh \| codex/gpt-5.6-sol@xhigh`                                                      |
> | `@xlarge`      | `claude/opus@max \|\| codex/gpt-5.6-sol@max \|\| grok/grok-4.6@max`                                 |

*See full plan file for details.*

