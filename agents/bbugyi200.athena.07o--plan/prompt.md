#gh:gh_sase-org__sase Can you help me add a way to "soft disable" specific LLM providers?

- We already support disabling LLM providers completely, which causes those models to be
  skipped in model pools and for fallback models (specified via the `||` syntax) to be
  used.
- The user should be able to specify (in the same TUI workflow they use now to disable
  an LLM provider--think hard about what the best user interface for this is) "soft
  disable" an LLM provider.
- Soft-disabled LLM providers should only be skipped in model pools if there is at least
  one other enabled model in that pool.
- Soft-disabled LLM providers should not trigger fallbacks to be used.
- This will allow me to decrease the amount of usage for a particular LLM provider while
  continuing to use that provider when necessary. This will be useful, for example, when
  my usage limit is approaching for a particular provider but I haven't hit it yet and
  still want to use that model for some agents.
- As a part of this change let's start adding better protections against the user
  attempting to use a (hard) disabled LLM provider.
  - We can support this by adding a new panel to the TUI that pops up if the user
    attempts to launch an agent that uses a disabled LLM provider (e.g. by specifying a
    model for that provider explicitly via the `%model` directive or by using a model
    pool with no enabled providers).
  - If the user attempts to launch several agents via an xprompt swarm, we should check
    each individual prompt in the swarm. If a swarm launches four agents, for example,
    but two of them require providers that are disabled, this should trigger this panel
    twice (in sequence, one at a time).
  - This new panel should offer the user a variety of options which they should be able
    to select via a single key press:
    - Abort this agent's launch.
    - Abort this agent swarm launch (only shown when the user attempted to launch a
      swarm of agents).
    - Re-enable one or more of the disabled LLM providers that triggered this panel and
      then launch the agent.
    - Use a different model to launch this agent.
- #beau

#plan