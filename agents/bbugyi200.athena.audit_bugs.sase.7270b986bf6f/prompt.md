#gh:sase-org/sase
%id(audit_bugs.sase.7270b986bf6f, tribe=chop)
%wait(runners=0)
#pr(recent_bug_audit_sase_7270b986bf6f)

Audit recent commits in sase for confirmed bugs.

The Axe `git.commits_since` trigger owns the threshold and checkpoint for scheduled
runs. Review the commit history through 7270b986bf6fbcd9055315469c631d2c586c2b5a, identify the recent
since-last-audit scope from the available history and task context, and inspect every
commit in that scope.

Inspect the commits in scope for correctness regressions, broken edge cases, unsafe
error handling, race conditions, data-loss risks, and test failures introduced by
those commits.

Fix confirmed issues only. Avoid unrelated improvements, style-only edits,
speculative refactors, broad rewrites, and preference changes. If no confirmed bug is
found, leave the worktree untouched and report that outcome.

When you change files, run the focused checks appropriate to the affected code. Use
the `#pr(recent_bug_audit_sase_7270b986bf6f)` rollover workflow if follow-up work is required.