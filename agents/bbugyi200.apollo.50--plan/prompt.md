#gh:gh_sase-org__sase I'm pretty sure the TUI was allowed to restart after a sase update (triggered by
the `,E` keymap) even though there was a sase agent swarm launching via the the
`#research_swarm` xprompt swarm (that I launched from the prompt input widget). This
restart should have been forced to wait for that proc to finish / for that agent swarm
to finish launching. Can you help me confirm/deny my suspicion, diagnose the true root
cause, and fix the issue?

#plan %m:@xlarge %auto