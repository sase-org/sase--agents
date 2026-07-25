%name:audit_bugs.sase.a452b461cf42
%w(runners=0)
#gh:gh_sase-org__sase %g:chop #pr(recent_bug_audit_sase_a452b461cf42)

Audit recent commits in sase for bugs.

Review scope:
- Marker file: /home/bryan/.sase/projects/gh_sase-org__sase/recent_bug_audit_marker
- Base selection: marker SHA 83b7e6be94fab92eb4b520f543169069de7aa157
- Commit range: 83b7e6be94fab92eb4b520f543169069de7aa157..a452b461cf42419b1403baae334608f834caeb46
- Current HEAD: a452b461cf42419b1403baae334608f834caeb46
- Commit count since marker: 202

Inspect every commit in this since-last-run range for confirmed bugs, correctness regressions, broken edge
cases, unsafe error handling, race conditions, data loss risks, or test failures introduced by these commits.

Fix confirmed issues only. Avoid unrelated improvements, style-only edits, speculative refactors, broad
rewrites, or preference changes. If no confirmed bug is found, leave the worktree untouched and report that
outcome.

When you change files, run the focused checks appropriate to the affected code.