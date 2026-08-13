%id(cld, clan=research.0f) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase Sase procs, which are currently called "tasks" but will soon
be renamed to "procs" (see the sase-lh epic bead) currently support processes that are
attached to the TUI and ones that are detatched. I would like to change this and migrate
all of the current procs that attach to a TUI to detached procs (we would then remove
the `sase task run` command's `-d|--detatched` option). I think the problem with this is
that the procs that attach to a TUI do not necessarily have a command associated with
them, which should be required for a detached proc (verify this is true).

Can you help me do some research into what it would take to migrate every existing proc
that attaches to a TUI to a detached proc by creating an associated command, if
necessary for that proc? (Maybe a `sase` sub-command or sub-sub-command? Think hard
about where this command should live.) #research