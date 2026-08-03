- **AGENTS:**
  - [bbugyi200.athena.ci_fix.sase.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ci_fix.sase.4/README.md)

[#gh:sase-org/sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%id(ci_fix.sase.@, tribe=chop) %wait(runners=0)
[#pr(ci_fix_sase_39ef28e, status=ready)](https://github.com/sase-org/sase/blob/fbe7a6fb6d2a6ee48a96c0de4e61245dfb813092/src/sase/xprompts/pr.yml)

[#actstat(repo=sase-org/sase)](https://github.com/bbugyi200/dotfiles/blob/0945392321d67fd9559dc06dcfcec7c94522648d/home/dot_config/sase/sase.yml#L205)

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/30771239483 Pinned failing commit: 39ef28e Failed jobs
from the sweep:

- test (3.12)
- test (3.13)

The pinned failure is on a settled commit older than the current unsettled HEAD
(fe0d71e09fc1ce0984d67df49917c8e2055c0b4b). Re-verify these job failures against current state before changing code.

First re-verify that this failure and commit are still current on the default branch. If it was superseded or already
fixed, leave the worktree unchanged and report that outcome. Keep any fix narrowly scoped and run the relevant checks.

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 1.1 KB</summary>

```markdown
IMPORTANT: You should make the necessary file changes, but should NOT create a commit, branch, or PR yourself.
Exception: If a post-completion finalizer instructs you to commit, you MUST follow those instructions and commit.

GitHub Actions is failing for the sase-org/sase repo. Can you run the `actstat` command to get more information about
the failing jobs, diagnose the root cause of these failures, and then fix them?

Repair the current default-branch CI failure in sase-org/sase.

Pinned failing run: https://github.com/sase-org/sase/actions/runs/30771239483 Pinned failing commit: 39ef28e Failed jobs
from the sweep:

- test (3.12)
- test (3.13)

The pinned failure is on a settled commit older than the current unsettled HEAD
(fe0d71e09fc1ce0984d67df49917c8e2055c0b4b). Re-verify these job failures against current state before changing code.

First re-verify that this failure and commit are still current on the default branch. If it was superseded or already
fixed, leave the worktree unchanged and report that outcome. Keep any fix narrowly scoped and run the relevant checks.
```

</details>

<!-- /sase:section:rendered -->
