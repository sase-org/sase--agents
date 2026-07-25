%name:audit_bugs.sase.fe372b13adbc
#gh:gh_sase-org__sase %g:chop #pr(recent_bug_audit_sase_fe372b13adbc)

Audit recent commits in sase for bugs.

Review scope:
- Marker file: /home/bryan/.sase/projects/sase/recent_bug_audit_marker
- Base selection: no marker file exists
- Commit range: first audit through fe372b13adbcbab41a9e52b2232e04ecfba82647
- Current HEAD: fe372b13adbcbab41a9e52b2232e04ecfba82647
- Commit count since marker: 999

Inspect every commit in this since-last-run range for confirmed bugs, correctness regressions, broken edge
cases, unsafe error handling, race conditions, data loss risks, or test failures introduced by these commits.

Fix confirmed issues only. Avoid unrelated improvements, style-only edits, speculative refactors, broad
rewrites, or preference changes. If no confirmed bug is found, leave the worktree untouched and report that
outcome.

When you change files, run the focused checks appropriate to the affected code.