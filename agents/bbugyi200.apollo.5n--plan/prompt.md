#gh:gh_sase-org__sase I would like to give sase plans (i.e. tales and epics) the ability to embed sase
gate options within their frontmatter somehow (note that recent research recommends an
altered approach that I agree with--see below for details). Can you help me implement
this?

- This will be useful, for example, to start requiring that all memory file changes be
  planned in plan files with explicit human gates (that should default to on iff the
  user explicitly requested those memory changes).
- This will also be useful if, for example, a sase agent has a question for the user
  that effects the plan but the agent has enough information to write a good plan
  without an immediate answer (i.e. the coder agent can implement the plan based on what
  gate selections the user made). Agents should prefer to ask user questions about the
  plan via this method (when possible to do so without degrading the quality of the
  plan) instead of using the /sase_questions skill.
- I have already done some research on this, which can be found in the
  plan_frontmatter_decisions.md and plan_decisions_cross_surface_ux.md files in the research sidecar repo.
  Review that research before planning. I agree with all of the recommendations made in
  those research files (though your judgement should take priority if you find genuine,
  verifiable concerns).
- #beau

#plan %m:@xlarge %auto