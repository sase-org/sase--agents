%name:research.@.cld %m:@research_b %g:research #gh:gh_sase-org__sase I would like to add support for running multiple agent children in the same family in parallel so I can support a few different use cases:
1. Running all phase agents and the agent that lands the epic in the same agent family
2. Doing the same thing for the research_swarm_kiss that lives in my chezmoi repo.

This will have several benefits, including saving space on the agents tab and allowing the user to see all of the agent metadata for all of the agents related to a particular Epic on a single panel. The root agent entry that contains all of the Epic agents should consolidate the metadata from all of them.

Can you do some research to help me understand how feasible this is and what other design decisions need to be made before we can start implementing this? End your analysis with a recommended solution #research