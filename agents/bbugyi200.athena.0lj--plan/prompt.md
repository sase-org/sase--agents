#gh:gh_sase-org__sase I just had to approve a tale plan proposed by the `sase-116.5.land` sase agent,
even though the prompt used to launch that agent included the `%auto` directive. I
believe this is likely because that agent ran a sase monitor and the `%auto` directive's
functionality didn't propagate to the most recent agent shell for some reason. Can you
help me confirm/deny my suspicion, diagnose the true root cause, and fix the issue?

#plan %m:claude-fable-5