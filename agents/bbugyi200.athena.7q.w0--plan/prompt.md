#gh:gh_sase-org__sase %w:7q Can you help me fix the `#research_swarm` xprompt to make some things clear to the final / consolidator research agent?

- This agent should create the new directory inside a directory of the form `<YYmmdd>` (represents the current month). We should give this directory to the agent explicitly using xprompt shell expansion with the `date +%y%%m` command.
- Make sure this agent understands that it is the lead researcher and as such it should perform its own research, which should be merged into the final result.
- Use best prompting practices here to make sure that we keep this prompt concise and meaningful. Every token in context is either helping us or hurting us.

#tale #m_fable