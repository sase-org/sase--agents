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
- #beau

#plan #m_opus