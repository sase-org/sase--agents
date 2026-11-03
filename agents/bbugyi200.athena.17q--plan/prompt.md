#gh:gh_sase-org__sase Can you help me add a new input to the `#research_swarm` macro that controls
whether we instruct the linker agent to convert tables to lists or not?

- Let's give this input a default value of `false`.
- My goal is to remove this functionality completely, but I'm not yet certain that I am
  okay with the way markdown tables are rendered once the markdown has been converted to
  a PDF (by the `bob ref create` command), so I want an easy way to re-enable it.
- Before submitting your plan, set some sase variables to express what you think of this
  plan (think hard about whether is the right move or not).

#plan %m:@xlarge