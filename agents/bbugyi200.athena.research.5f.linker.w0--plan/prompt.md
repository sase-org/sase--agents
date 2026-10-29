#gh:gh_sase-org__sase I think we made a mistake having sase gates (including and especially plans) and
sase monitors kill the agent that invoked them. I would like to start requiring that
agents use a finalizer for gates and monitors instead. Can you help me implement this?

- I'm thinking that the best way to do this is probably to just use the existing commit
  finalizer.
- This means that, after this change, all agent turns should be required to submit a
  final declaration (agents that proposed plans or ran monitors used to be excempt). We
  will need to make sure that the commit finalizer knows that it is okay for agents that
  propose plans or run monitors do not specify that a commit should be made.
- The benefits of this change:
  - Using finalizers to perform an agent's final action seems more intuitive than what
    we were doing before.
  - On a more practical note, this will give agents the ability to commit file changes
    and propose plans in the same turn. See the `bob-cli-dw.land` and `sase-1ou.land`
    sase agents for some context on why this might be useful.
- Review the staged_handoffs_through_host_completion.md file in the research sidecar
  repo for context and inspiration before planning. I agree with all of the requirements
  recommended in that research file (but keep in mind that you are responsible for
  planning and splitting up this work appropriately).

#plan %m:@xlarge %w:research.5f.linker