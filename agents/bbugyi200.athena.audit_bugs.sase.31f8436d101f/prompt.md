%name:audit_bugs.sase.31f8436d101f
#gh:gh_sase-org__sase %g:chop #pr(recent_bug_audit_sase_31f8436d101f)

Audit recent commits in sase for bugs.

Review scope:
- Marker file: /home/bryan/.sase/projects/gh_sase-org__sase/recent_bug_audit_marker
- Base selection: marker SHA missing; using marker timestamp 1783336197
- Commit range: commits after unix timestamp 1783336197 through 31f8436d101f62c344dc4f30376dd9dd5569731d
- Current HEAD: 31f8436d101f62c344dc4f30376dd9dd5569731d
- Commit count since marker: 201

Inspect every commit in this since-last-run range for confirmed bugs, correctness regressions, broken edge
cases, unsafe error handling, race conditions, data loss risks, or test failures introduced by these commits.

Fix confirmed issues only. Avoid unrelated improvements, style-only edits, speculative refactors, broad
rewrites, or preference changes. If no confirmed bug is found, leave the worktree untouched and report that
outcome.

When you change files, run the focused checks appropriate to the affected code.