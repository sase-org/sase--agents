#gh:gh_sase-org__sase The Muse LLM provider is using its own harness to wait for background commands.

- That should not be allowed when Muse is running as a sase agent.
- Review the provider_wait_contract_early_exits.md file in the research sidecar repo for
  context.
- That research file recommends that I allow Muse agents to use their own harnesses'
  command monitoring functionality but I would rather Muse agents use sase monitors for
  this.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea or should I prefer
agent's use their own command monitoring utilities when possible? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research %m:@xlarge