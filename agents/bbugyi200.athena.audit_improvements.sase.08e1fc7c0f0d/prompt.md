#gh:sase-org/sase
%id(audit_improvements.sase.08e1fc7c0f0d, tribe=chop)
#pr(recent_improvement_audit_sase_08e1fc7c0f0d)

Audit recent commits in sase for objective improvements.

The Axe `git.commits_since` trigger owns the threshold and checkpoint for scheduled
runs. Review the commit history through 08e1fc7c0f0d871dfd0b6850b96f3f2ac30a12ce, identify the recent
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
the `#pr(recent_improvement_audit_sase_08e1fc7c0f0d)` rollover workflow if follow-up work is required.