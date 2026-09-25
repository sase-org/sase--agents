#gh:gh_sase-org__sase I want to add support for integrating an LLM provider's usage metrics into
sase. Can you help me implement this?

- In particular, users that are using their subscription instead of the API for the
  given provider are interested in how much usage they have remaining until they hit a
  limit.
- We should support this in a generic fashion that allows us to easily add support for
  any new LLM provider that might get added to sase in the future.
- We may eventually integrate input/output token usage, billing data, and other
  statistics for API users as well but this will not be a part of our initial solution.
- To start I was planning on implementing this for only the Claude provider, the Codex
  provider, and the Grok provider.
- Review the provider_subscription_usage.md and subscription_capacity_experience.md
  files in the research sidecar repo for context and inspiration before planning.

#plan %m:@xlarge