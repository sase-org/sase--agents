#gh:sase-org/sase
%id(audit_bugs.sase.@, tribe=chop)
%wait(runners=0)
#pr(recent_bug_audit_sase_8658abee6a73)

Audit recent commits in sase for confirmed bugs.

The Axe `git.commits_since` trigger owns the threshold and checkpoint for scheduled
runs. Review the commit history through 8658abee6a733ddadd7b4b5bb01225ec66c8300d, identify the recent
since-last-audit scope from the available history and task context, and inspect every
commit in that scope.

Inspect the commits in scope for correctness regressions, broken edge cases, unsafe
error handling, race conditions, data-loss risks, and test failures introduced by
those commits.

Fix confirmed issues only. Avoid unrelated improvements, style-only edits,
speculative refactors, broad rewrites, and preference changes. If no confirmed bug is
found, leave the worktree untouched and report that outcome.

When you change files, run the focused checks appropriate to the affected code. Use
the `#pr(recent_bug_audit_sase_8658abee6a73)` rollover workflow if follow-up work is required.