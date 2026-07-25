#gh:sase-org/sase
%name:audit_bugs.sase.09fa3fe1e8b6
%tribe:chop
#pr(recent_bug_audit_sase_09fa3fe1e8b6)

Audit recent commits in sase for confirmed bugs.

The Axe `git.commits_since` trigger owns the threshold and checkpoint for scheduled
runs. Review the commit history through 09fa3fe1e8b6a29532127ade5be2e020fd06388a, identify the recent
since-last-audit scope from the available history and task context, and inspect every
commit in that scope.

Inspect the commits in scope for correctness regressions, broken edge cases, unsafe
error handling, race conditions, data-loss risks, and test failures introduced by
those commits.

Fix confirmed issues only. Avoid unrelated improvements, style-only edits,
speculative refactors, broad rewrites, and preference changes. If no confirmed bug is
found, leave the worktree untouched and report that outcome.

When you change files, run the focused checks appropriate to the affected code. Use
the `#pr(recent_bug_audit_sase_09fa3fe1e8b6)` rollover workflow if follow-up work is required.