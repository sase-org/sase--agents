#gh:gh_sase-org__sase Can you help me fix the claude provider so claude sase agents no longer fail
because the agent attempted to wait for some background process to wake them (which will
never happen since sase agents are single-turn)? See the `0km` sase agent's chat for
context. Think hard about what the most appropriate and reliable fix for this issue is.

#plan %m:claude-fable-5