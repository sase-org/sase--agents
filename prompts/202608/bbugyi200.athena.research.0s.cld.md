- **AGENTS:**
  - [bbugyi200.athena.research.0s.cld](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.0s.cld/README.md)

%id(cld, clan=research.0s) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase
Sase's commit finalizer is currently a hard-coded part of the system.

- I would like to generalize the concept of sase's finalizer so users can define their
  own finalizers via plugins and/or configuration.
- I think we should also consider supporting a new `%final` directive to override the
  finalizer for a specific sase agent.
  - I'm thinking this could then default to something like `%final:commit` if not used
    explicitly in a sase agent's prompt?
- One way to implement this is to add a new `/sase_final` xprompt skill and tell agents
  that they must invoke it at the end of every turn (sase agents that get intentionally
  terminated early--when using their /sase_plan or /sase_monitor skills, for
  example--are exempt).
  - The finalizer could then force a new turn if the agent doesn't use /sase_final for
    some reason (and then fail if the agent doesn't use /sase_final on that turn
    either).
  - This skill could instruct agents how to use a new `sase final` command to persist
    some JSON data somewhere that is associated with that agent and can be read,
    validated, and acted on (e.g. by creating commits, creating task beads, etc...) by
    the finalizer.
  - We should figure out a way for agents to specify the commits/stitches that should be
    created for each repo that contains files that that agent modified using the
    `sase final` command. We'll also need to be careful that we don't break sase's
    current merge conflict workflow (e.g. make sure merge conflicts are still always
    caught and handled by sase agents--when they can't be auto-resolved). Think hard
    about how to get this right.
    - One new requirement we should add: sase agents that do not commit to certain repos
      should be required to specify a refusal reason via the `sase final` command (so we
      have some more insight when the finalizer fails because an agent refused to commit
      detected file changes).
- Sase's commit finalizer is such a critical part of sase that I think this feature
  belongs behind a feature flag.

Can you do some research with the goal of helping me decide the best way to implement
this? We've already done some related research on this in the past so make sure you find
and review that before starting your own investigation. That research is old though so
don't rely on it as a source of truth. End your analysis with a recommended solution.
#research
