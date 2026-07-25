#gh:gh_sase-org__sase #fork:gy.f1 Can you now help me get rid of the `@phase_worker` model
alias and just define the `@medium_phase_worker` alias to use `@default` as its
value instead of `@phase_worker`?

- Also, let's rename the `@cheapest` model alias to `@cheaper` and define a new
  model alias using the old `@cheapest` model alias name (this new version
  should not be used by any other model aliases yet) that is defined with a
  value of `claude/sonnet | codex/gpt-5.3-codex-spark`.
- Also, let's make sure that an agent that configures a model explicitly for a
  specific phase is able to do so for any phase size.
- Finally, stop telling agents about model aliases in the `/sase_plan` skill.
  They shouldn't need to know the inner workings of sase. They just need to know
  that:
  - small phase agents will not create plans
  - medium/large agents will create plans
  - the phase sizes also determine how smart of a model we will use (by default,
    assuming the agent hasn't overridden the model for that phase)

#plan