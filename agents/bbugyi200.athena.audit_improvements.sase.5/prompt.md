#gh:sase-org/sase
%id(audit_improvements.sase.@, tribe=chop)
%wait(runners=0)
#pr(recent_improvement_audit_sase_a76461812e1f)

Audit recent commits in sase for objective improvements.

The Axe `git.commits_since` trigger owns the threshold and checkpoint for scheduled
runs. Review the commit history through a76461812e1fdf1a6661dbb790bd8fc54ed95300, identify the recent
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
the `#pr(recent_improvement_audit_sase_a76461812e1f)` rollover workflow if follow-up work is required.