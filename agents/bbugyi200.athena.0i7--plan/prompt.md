#gh:gh_sase-org__sase We currently seem to rename agents that were auto-named using the `.w<N>`
suffix, which we use when an agent with no explicit name that waits for a single other
agent is launched, after the agent has launched sometimes. I suspect that this happens
when users change that agent's dependencies after launching it (e.g. using the `w`
keymap on the "Agents" tab), but I'm not sure. We should not do this since it breaks any
dependencies other agents had on that agent (since its name changed). Can you help me
confirm/deny my suspicion, diagnose the true root cause, and fix the issue?

#plan %m:@xlarge %q:3