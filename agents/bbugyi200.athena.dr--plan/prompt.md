#gh:gh_sase-org__sase Can you help me change the way that the `%clan` and `%tribe` directives
interact?

- These two directives should never be allowed in the same prompt. If they are,
  we should produce a useful error message to the user.
- We should instead add a new `tribe` keyword argument to the `%clan` directive
  that takes the tribe name of the tribe that the clan should join as a value.
- We are making this change in order to make the invalid case of attempting to
  have an agent/agent family join a different clan than the one its tribe is a
  part of impossible to express (if `tribe` is specified by multiple agents in
  the same clan then the clan will belong to the tribe specified by the last
  agent that was launched).
- Make sure you update all relevant xprompts in this repo and in my chezmoi
  repo.

#plan