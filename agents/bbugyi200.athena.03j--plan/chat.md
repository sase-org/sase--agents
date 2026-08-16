# Chat History - ace-run (03j--plan)

- **TIMESTAMP:** 2026-08-16 10:33:04 EDT
- **MODEL:** claude/opus
- **AGENT:** 03j--plan

**Plan:** /home/bryan/.sase/plans/202608/llm_usage_limit_auto_disable.md


## Prompt

#gh:gh_sase-org__sase Can you help me add automatic detection of error messages from LLM providers
that indicate that the user has hit their usage limit?

- When a sase agent fails and its error output matches a configured (via a new sase
  config field) pattern for the corresponding LLM provider, then we should automatically
  disable that provider for a configurable (using a new sase config field--default to 24
  hours).
- Make sure we have excellent default configured patterns for all supported sase LLM
  providers. See if you can find historical failures in sase's logs that show you the
  exact types of error messages you can expect when usage limits are hit for each
  provider.
- Also make sure users have an easy way of overriding or adding to this configuration.
- See how we do this for sase agent retries for inspiration.
- After disabling the LLM provider, we should send a rich, sase notification to the user
  with useful information about what provider was disabled, for how long, and what
  triggered the event.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/llm_usage_limit_auto_disable.md`

> # Plan: Auto-disable LLM providers on usage-limit errors
> ## Why
> Today, when a provider reports a usage limit, every sase agent routed to that provider
> keeps failing. Worse, the retry subsystem actively makes it worse: the `codex` built-in
> retry patterns include `"rate limit"` and `"429 Too Many Requests"`, so a usage-limit
> failure is classified as _retryable_ and the agent sleeps `60s`, then `300s`, then
> `1800s` before failing anyway. Meanwhile every other agent launched during the outage
> repeats the same cycle.
> sase already has the exact mechanism needed to fix this, and it is fully wired:
> `TemporaryProviderDisable` (`src/sase/llm_provider/provider_disable.py`, backed by

*See full plan file for details.*

