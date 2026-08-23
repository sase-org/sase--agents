#gh:gh_sase-org__sase The `sase-s9.3` and `sase-s9.4` sase agents both failed to use their /sase_final skills at the end of their turn. The final declaration recovery process then forced them into another turn at which point they submitted the finalization payload to create a commit, which was created successfully. The bead that was associated with these agents was never closed, which I was under the impression should always be done unless the `-B|--do-not-close-bead` option was used with the `sase stich create` command. So there are two problems to solve here:

1. We're not making it clear enough in agent instruction files that agents must use their /sassy_final skill at the end of their turn.
2. Even if an agent forgets to do this, the commit they create via finalization after being nudged by the finalizer should auto-close the bead, which doesn't appear to be happening today.

Can you do some research into the best way to fix these issues and then fix them? #plan