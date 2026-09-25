#gh:gh_sase-org__sase Can you help me add support to the `%if` directive for accepting a new
`should_run=<true|false>` keyword input that can be used to make an agent in an xprompt
swarm conditional?

- This input should be mutually exclusive with the `%if` directive's positional
  python/bash input (fail with a good error if both are provided).
- Unlike the python/bash positional input that the `%if` directive currently accepts,
  this directive should cause the xprompt swarm to run as though that agent's prompt
  block (i.e. the `---` and that agent's prompt) were not even included in the xprompt
  swarm definition (i.e. the markdown file that defined the xprompt swarm). When the
  python/bash input is used, on the other hand, an agent is always launched.
- As our first use-case, I want to add a new `should_generate_image=<true|false>` input
  to the `#research_swarm` xprompt swarm and add
  `%if(should_run={{ should_generate_image }])` to the prompt of the sase agent in that
  swarm that generates an infographic. The goal of this change is to make the image
  generator sase agent optional. Disable image generation by default (i.e. the default
  value of the new `should_generate_image` input should be `false`).

#plan %m:gpt-6-astra