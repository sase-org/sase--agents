#gh:gh_sase-org__sase If the user were to press `<enter>` in #sshot, they would receive an error
because of the `bead=sase-hq.3` kwarg since that bead is already in-progress, even
though we have specified (via the `!` prefix to the `%id` directive's first input) that
we want to overwrite the previous agent of the same name (which was the assignee of that
bead). Can you help me fix this? This validation should not fire when the assignee is
going to be overwritten.

#plan