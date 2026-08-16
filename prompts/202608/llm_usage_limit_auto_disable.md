- **PLAN:**
  [202608/llm_usage_limit_auto_disable.md](https://github.com/sase-org/sase--plans/blob/main/202608/llm_usage_limit_auto_disable.md)
- **AGENTS:**
  - [bbugyi200.athena.03j--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03j.md)

Can you help me add automatic detection of error messages from LLM providers that
indicate that the user has hit their usage limit?

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
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
