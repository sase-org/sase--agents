#gh:gh_sase-org__sase File changes keep being made to the
~/projects/github/sase-org/sase/sase/repos/beads/ directory, which is auto-synced (by a
sase job I believe). These file changes (see the most recent git stash in that
repo/directory for an example) cause that auto-sync to fail, which cause agents that are
waiting for closed beads to continue waiting (because the `wait_checks` job can't see
that the beads are closed because the beads sidecar repo that it is reading is
out-of-date). All changes to beads directories are supposed to be made to sidecar repos
in ephemeral workspaces (the goal is to make sure these changes are always committed and
never made to a shared directory).

Can you help me confirm/deny my suspicion, diagnose the true root cause, and fix the
issue? Think hard about what the appropriate fix is here to make sure that your fix
doesn't break any previous, related fixes. #plan %m:claude-fable-5 %q:10