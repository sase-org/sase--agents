#gh:gh_sase-org__sase I haven't seen the `@epic` agent tribe panel disappear in a while, but I am
seeing the agent nodes in that panel flicker (the LLM provider icons are removed and
then re-added, for example--it is hard to see what changes exactly because it happens so
quickly).

- We tried to fix this earlier today and seem to have partially succeeded (see the
  sase-12p epic bead for context).
- I think this might have something to do with the fact that some agent nodes don't seem
  to load until after a delay when the TUI starts up.

Can you help me confirm/deny my suspicion, diagnose the true root cause, and fix the
issue? #plan %m:gpt-6-astra