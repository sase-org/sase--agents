#gh:gh_sase-org__sase #fork:gy Can you now help me add a new `@cheapest` builtin model alias
as well that is configured to load-balance between the `claude/opus@medium` and
`codex/gpt-5.5` models?

- We will need to add support for model alias load-balancing for this new model
  alias, which should have a value of `claude/opus@medium | codex/gpt-5.5` (we will
  use `|` to specify that a model alias uses load balancing).
- When a sase agent is launched that configures a load-balancing model alias
  (e.g. using the `%model` directive), we should select the next model in the
  load-balancers model pool for this alias (i.e. the list of models that were
  provided, using `|` to separate them) to use when launching this agent. This
  means we will need to start tracking when these model aliases are used.
- We should also be able to use this model alias load-balancing syntax to ensure
  a fallback is used in-case one of the specified model's agent CLI providers is
  not installed (ex: if the user does not have codex installed, the `@cheapest`
  model alias should always render to `claude/opus@medium`).
- We should configure the `@small_phase_worker` model alias to use `@cheapest`
  as its value. Also, let's start defining `@large_phase_worker` to use
  `@smartest` as its value.

#plan #m_fable