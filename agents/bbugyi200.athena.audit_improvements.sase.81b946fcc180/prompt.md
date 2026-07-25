#gh:sase-org/sase
%name:audit_improvements.sase.81b946fcc180
%tribe:chop
#pr(recent_improvement_audit_sase_81b946fcc180)

Audit recent commits in sase for objective improvements.

The Axe `git.commits_since` trigger owns the threshold and checkpoint for scheduled
runs. Review the commit history through 81b946fcc1805516a2da00ebc7366e0a3f96889c, identify the recent
since-last-audit scope from the available history and task context, and inspect every
commit in that scope.

Inspect the commits in scope for clear, objective wins: a small
correctness-preserving simplification, a plainly better error path, targeted test
coverage for changed behavior, or an obvious low-risk performance fix.

Only change files when the value is objective and narrowly scoped. Do not perform
style churn, speculative refactors, preference changes, broad rewrites, renames,
formatting-only edits, or subjective cleanup. If no objectively valuable change is
found, leave the worktree untouched and report that outcome.

When you change files, run the focused checks appropriate to the affected code. Use
the `#pr(recent_improvement_audit_sase_81b946fcc180)` rollover workflow if follow-up work is required.