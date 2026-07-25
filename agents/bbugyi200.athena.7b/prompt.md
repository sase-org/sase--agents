#gh:gh_sase-org__sase I want to add the ability to configure a maximum number of sase agents that are allowed to be running at any given time. Can you help me implement this?

- I want the user to be able to override this both in their personal config but also on a prompt-by-prompt basis using an xprompt directive.
- I think we can accomplish this by using a new `runners` keyword argument to the existing `wait` directive, so users can override this in prompts (a prompt that sets runners to 0, for example, would wait until there are no agents running before it runs). 
- We should have a sase configuration field that defaults to 10 for this.
- While waiting for other agents to finish, we should use the standard waiting agent status for this, but make sure that it is clear at a glance that an agent is waiting because of this new configuration / `wait` key word.
- #beau 

#epic #m_fable