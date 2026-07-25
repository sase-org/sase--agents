%name:audit_bugs.sase.1180425d1192
#gh:gh_sase-org__sase %g:chop #pr(recent_bug_audit_sase_1180425d1192)

Audit recent commits in sase for bugs.

Review scope:
- Marker file: /home/bryan/.sase/projects/gh_sase-org__sase/recent_bug_audit_marker
- Base selection: marker SHA 31f8436d101f62c344dc4f30376dd9dd5569731d
- Commit range: 31f8436d101f62c344dc4f30376dd9dd5569731d..1180425d1192c6a3017aece24f67524a19b942dd
- Current HEAD: 1180425d1192c6a3017aece24f67524a19b942dd
- Commit count since marker: 202

Inspect every commit in this since-last-run range for confirmed bugs, correctness regressions, broken edge
cases, unsafe error handling, race conditions, data loss risks, or test failures introduced by these commits.

Fix confirmed issues only. Avoid unrelated improvements, style-only edits, speculative refactors, broad
rewrites, or preference changes. If no confirmed bug is found, leave the worktree untouched and report that
outcome.

When you change files, run the focused checks appropriate to the affected code.