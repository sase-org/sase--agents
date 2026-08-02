- **AGENTS:**
  - [bbugyi200.athena.audit_improvements.sase.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.audit_improvements.sase.3/README.md)

[#gh:sase-org/sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%id(audit_improvements.sase.@, tribe=chop) %wait(runners=0)
[#pr(recent_improvement_audit_sase_fbe7a6fb6d2a)](https://github.com/sase-org/sase/blob/fbe7a6fb6d2a6ee48a96c0de4e61245dfb813092/src/sase/xprompts/pr.yml)

Audit recent commits in sase for objective improvements.

The Axe `git.commits_since` trigger owns the threshold and checkpoint for scheduled runs. Review the commit history
through fbe7a6fb6d2a6ee48a96c0de4e61245dfb813092, identify the recent since-last-audit scope from the available history
and task context, and inspect every commit in that scope.

Inspect the commits in scope for clear, objective wins: a small correctness-preserving simplification, a plainly better
error path, targeted test coverage for changed behavior, or an obvious low-risk performance fix.

Only change files when the value is objective and narrowly scoped. Do not perform style churn, speculative refactors,
preference changes, broad rewrites, renames, formatting-only edits, or subjective cleanup. If no objectively valuable
change is found, leave the worktree untouched and report that outcome.

When you change files, run the focused checks appropriate to the affected code. Use the
`#pr(recent_improvement_audit_sase_fbe7a6fb6d2a)` rollover workflow if follow-up work is required.

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 1.3 KB</summary>

```markdown
IMPORTANT: You should make the necessary file changes, but should NOT create a commit, branch, or PR yourself.
Exception: If a post-completion finalizer instructs you to commit, you MUST follow those instructions and commit.

Audit recent commits in sase for objective improvements.

The Axe `git.commits_since` trigger owns the threshold and checkpoint for scheduled runs. Review the commit history
through fbe7a6fb6d2a6ee48a96c0de4e61245dfb813092, identify the recent since-last-audit scope from the available history
and task context, and inspect every commit in that scope.

Inspect the commits in scope for clear, objective wins: a small correctness-preserving simplification, a plainly better
error path, targeted test coverage for changed behavior, or an obvious low-risk performance fix.

Only change files when the value is objective and narrowly scoped. Do not perform style churn, speculative refactors,
preference changes, broad rewrites, renames, formatting-only edits, or subjective cleanup. If no objectively valuable
change is found, leave the worktree untouched and report that outcome.

When you change files, run the focused checks appropriate to the affected code. Use the
`#pr(recent_improvement_audit_sase_fbe7a6fb6d2a)` rollover workflow if follow-up work is required.
```

</details>

<!-- /sase:section:rendered -->
