# Chat History - ace-run (0ce--plan)

- **TIMESTAMP:** 2026-08-24 10:28:51 EDT
- **MODEL:** claude/opus
- **AGENT:** 0ce--plan

**Plan:** /home/bryan/.sase/plans/202608/provider_drain.md


## Prompt

#gh:gh_sase-org__sase Sase already has support for automatically detecting when a usage limit is hit
and auto-disables the corresponding LLM provider in that case. The problem is that we
don't do anything about the agents that failed with the usage limit error or currently
running/waiting agents that are using that provider (which will presumably fail since
we've hit our usage limit). Can you help me fix this by auto-relaunching any
failed/running/waiting agent using a provider when we disable that provider?

- This should happen automatically when a usage limit is detected. Make sure we improve
  the usage limit notification that is already sent to the user to provide useful
  information about which agents were relaunched.
- If the user manually disables a provider from the TUI then they should be prompted
  whether they want to re-launch existing agents or not.
- We already have support for relaunching agents in this codebase, including a command
  line utility to do so. Try to reuse existing code/logic when possible.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/provider_drain.md`

> # Plan: Drain stranded agents when an LLM provider is disabled
> ## 1. Context
> SASE already detects provider usage limits and writes a temporary machine-wide provider
> disable. `sase.llm_provider.usage_limit_disable.handle_possible_usage_limit()` matches
> the provider's error text, wins a first-writer disable window through
> `try_disable_provider*`, and sends one notification through
> `sase.notifications.senders.notify_provider_usage_limit_disabled()`. New launches then
> route around the provider: `sase.agent.launch_guard` refuses a unit whose only route is
> a hard-disabled provider, and model-alias resolution skips disabled pool members.
> Nothing happens to the agents that are already alive. The agent that hit the limit

*See full plan file for details.*

