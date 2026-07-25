# Chat History - ace-run

- **TIMESTAMP:** 2026-07-07 16:25:48 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** 0w--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-0w__plan-260707_155434.md`
- **2. --code** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260707_155434.md`

## Prompt

%model:@claude_coder
#gh:gh_sase-org__sase @sdd/tales/202607/gh_ref_tui_credential_freeze.md

The above plan has been reviewed and approved. Implement it now.


## Response

I’ll first load the SASE memory-read instructions because this touches TUI responsiveness, then I’ll inspect the approved plan and code paths before editing.

I’m going to read the TUI performance memory through the audited command, then compare the plan with the current implementation.

The plan requires changes in this repo plus the `sase-github` linked repo. I’ll open the matching linked workspace with `sase workspace open` and use that path for all linked-repo reads and edits.

I’m checking the provider hook plumbing and the existing GitHub plugin behavior now, plus current worktree status so I don’t disturb unrelated changes.

Both worktrees are clean. The current provider API only has a mutating `resolve_ref`, so I’m going to add the read-only hook and then switch completion base-dir lookup to it.

I’ve found the exact completion path and the GitHub clone path. Next I’m reading the listed remote-git call sites so the environment guard is applied consistently instead of only fixing the immediate clone.

The VCS provider uses a shared command runner for most git operations. I’m checking that runner before deciding whether to guard individual calls or the centralized path.

Most VCS git commands are centralized through `CommandRunner`; I’ll harden that shared runner for git commands and still add explicit guards where the code bypasses it.

I’m also checking the GitHub ref-resolution helpers and tests so the new peek hook can share existing read-only lookup logic instead of copying behavior loosely.

The GitHub plugin already separates project records and repo-path resolution enough to factor a read-only path. I’m going to make that explicit and update the clone URL/error handling at the same time.

Before editing, I’m checking the test harness shape for dev-update runners and provider hooks so the new API remains covered by existing hook contract tests.

The dev-update injected runner does not accept env kwargs, so I’ll guard its default subprocess runner and the direct `version._git.run_git` path without changing the runner protocol.

The VCS streaming runner is currently unused, so the remote-git hardening can stay on the normal subprocess runner and the explicit clone/fetch paths.

I’m going to edit the provider API, completion resolver, git environment helper, and GitHub plugin now. The edits are scoped to read-only completion resolution plus non-interactive subprocess guards.

I’m applying the SASE repo changes first: new `peek_ref`, read-only completion lookup, and subprocess prompt suppression for git.

The SASE repo API and guard edits are in place. I noticed `run_git` can be called with a custom runner, so I’m tightening that path to avoid passing subprocess-only kwargs to injected runners.

Now I’m editing the GitHub workspace plugin: adding the read-only `ws_peek_ref`, switching clones to SSH-first with HTTPS fallback, and disabling prompts for `git` and `gh` subprocesses.

The first GitHub patch missed one end-of-file context, so I’m splitting it into smaller patches to keep the edits precise.

I’ve added the hook entry point in the GitHub plugin. Next I’m replacing the clone helper with SSH-first, non-interactive attempts.

Clone handling is now SSH-first with captured, non-interactive failures. I’m hardening the GitHub CLI calls next.

I’m adding the read-only GitHub ref resolver by factoring the existing alias/project/ChangeSpec lookup into a shared helper and adding a repo-path peek that only uses existing local checkouts.

The repo-path peek now refuses to clone or write project records. I’m refactoring `resolve_gh_ref` so normal launches still use the mutating path while completion uses the read-only helper.

Launch resolution still clones through `resolve_gh_ref`; completion can now call `peek_gh_ref`. I’m updating the PR-related `gh` subprocesses to use the same prompt-disabled environment.

The direct PR commands are guarded. I’m adding the small environment helper used by those `gh` calls.

I’m adding the `gh` environment helper with a generic mapping type so it can layer over `os.environ` or test-provided envs.

The GitHub plugin changes are in. I’m updating focused tests now, and I’ll also scan for exact subprocess assertions that need the new `env`/`stdin` kwargs.

While adding tests, I caught one important issue: the peek path must not run even local git commands on the TUI thread. I’m adjusting peek results to avoid `get_default_branch`; launch-time resolution still computes the real checkout target.

The peek path now avoids `git` subprocesses entirely. I’ll add tests that enforce that and then update the clone expectations.

I’m adding the SASE-side unit tests for read-only completion, non-interactive git env, and guarded subprocess defaults.

The completion tests now assert `peek_ref` is used and `resolve_ref` is not. I’m adding tests for the git environment helper and clone materializer guard.

The workspace utility test now checks the prompt-suppression env. I’m adding coverage for the shared VCS command runner and dev-update default runner.

The VCS runner test is in place. I’m adding a default dev-update subprocess test so `git fetch` through that path also stays non-interactive.

That patch missed the exact test helper body. I’ll place the new dev-update test using the current file structure.

I found the right insertion point in `test_execute.py`; applying the dev-update subprocess test there.

The dev-update runner is covered. I’m adding a lower-level `run_git` test because detect/plan use that helper directly.

The git-helper test file has a different order than expected, so I’ll insert the new test after the fetch helper tests.

I’ll insert the `run_git` prompt-suppression test immediately after the fetch helper assertions.

The following test name is different, so I’m using a narrower insertion after the exact assertion block.

The file ends right after the fetch helper tests, so I’ll append the new test at EOF.

Appending the focused `run_git` test at the end of the helper test file.

SASE-side tests are updated. I’m moving to the `sase-github` tests for SSH-first clone behavior, HTTPS fallback, non-interactive env, and `ws_peek_ref`.

I’m updating the host-aware clone expectations from “HTTPS for non-configured owners” to “SSH first for every owner.”

The clone tests now cover SSH-first, port-aware SSH URLs, fallback, and both-failure diagnostics. I’m checking the surrounding test syntax after removing the old `github_orgs` patch.

The syntax is good. I’m checking the next block where repo-path resolution expected the old HTTPS URL.

Repo completion now gets `GH_PROMPT_DISABLED`, so I’m extending that test to assert the prompt guard as well as `GH_HOST`.

I’m adding `ws_peek_ref` tests that explicitly fail if the peek path tries to spawn a subprocess.

`ws_peek_ref` coverage is in. I’ll scan for remaining old `github_orgs` clone assumptions and exact URL assertions.

The remaining `github_orgs` references are submission-related, not clone selection. I’m checking the PR submit tests for exact kwargs sensitivity.

Before running checks, I’m checking the linked repo’s local agent instructions in case it has its own build or verification requirements.

No linked-repo `AGENTS.md` was present. I’m installing editable dependencies in both workspaces before formatting/checking, as the primary repo instructions require that before `just check`.

The linked repo `just install` failed before installing because its declared `sase>=0.11.0` dependency is not satisfiable from the configured index. The primary repo install is still building; I’m waiting on that before formatting and checks.

While the primary install continues, I’m inspecting the linked repo’s install/check recipes so I can choose the least invasive verification path after the dependency resolution failure.

The linked repo supports an override path during install; after the primary install finishes, I’ll retry linked install with the primary `sase` workspace as the local dependency override.

Primary install completed. I’m retrying the linked repo install with the local primary repo as the dependency override.

Both installs are now usable. I’m running the repo formatters before the targeted tests/checks.

Formatting completed cleanly. I’m running focused tests in both repos before the full `just check` runs so failures are easier to isolate.

Focused tests passed in both repos. I’m checking the diff/status briefly before running the full `just check` suite.

The focused diffs look scoped. I’m starting full `just check` in both repos now; the primary one may take longer because it includes the full test suite.

The linked repo full check passed. The primary repo failed only on mypy’s typing for dynamic `**kwargs` into `subprocess.run`; I’m replacing those with explicit `env`/`stdin` arguments so the behavior is unchanged but typed.

The typing fix is in. I’m formatting the primary repo again, then I’ll rerun the failed check.

Formatting is clean after the typing change. I’m rerunning primary `just check`; the linked repo already passed.

Primary lint/mypy passed; the full test portion is still running.

Validation has passed and tests are continuing. I’m waiting for the final result rather than interrupting the check.

The primary check is still in the test phase with no failure output yet.

Still waiting on the full primary test suite. No errors have surfaced in the output so far.

The check is still running; I’ll keep polling until it exits so the final status is accurate.

Primary `just check` passed. I’m doing a final status and diff summary pass in both repos so I can report exactly what changed.

The status shows only the intended source/test files in the two repos. I’m doing one final code skim around the changed helper paths.

The final skim looks consistent: completion uses peek-only paths, launch resolution still mutates when intended, and the full primary check has already passed. I’m confirming no protected memory/provider shim files were modified.

Implemented the approved plan across `sase` and `sase-github`.

Key changes:
- Added `ws_peek_ref` / `peek_ref` plumbing and switched prompt completion to read-only ref lookup.
- Added non-interactive git environment handling and applied it to clone/fetch/remote-capable git paths.
- Updated GitHub clone behavior to SSH-first with HTTPS fallback, both non-interactive.
- Added GitHub `ws_peek_ref` that resolves only existing local state and never clones or spawns subprocesses.
- Added focused regression tests for completion, prompt suppression, SSH fallback, and GitHub peek behavior.

Verification passed:
- `just check` in `sase`
- `SASE_CORE_PATH=<local sase repo> just check` in `sase-github`

Note: plain `sase-github` install could not resolve its declared `sase>=0.11.0` from the configured index, so I used its existing local override mechanism for install/check.

I made the listed changes in this session, so I’ll use the required SASE commit workflow for the main repo and the linked `sase-github` repo, then verify both worktrees are clean.

I’ve recorded the commit skill usage. I’m checking status and diffs in both repositories now so each commit only stages the files from this change set.

The diffs match the approved implementation: main repo has the provider API, prompt-completion, git environment, and tests; `sase-github` has the GitHub provider behavior and tests. I’m committing the main repo first with only the listed files staged.

The main repo commit is in progress; the commit wrapper is running its precommit step and dispatching through the configured VCS provider.

The main repo commit completed successfully. I’m verifying its status now, then I’ll commit the linked `sase-github` changes from that repository.

The main worktree is clean after the commit. I’m creating the linked repo commit message and committing only the GitHub plugin files listed by the finalizer.

I’m running the linked repository commit through the same SASE wrapper now.

The linked repo commit also completed. I’m checking the linked repo status for cleanliness, then I’ll do one final status check on the main repo.

Committed the changes in both repositories via `sase_git_commit`.

- `sase`: `fix: avoid credential prompts during ref completion`
- `sase-github`: `fix: make GitHub ref lookup credential-free`

Both worktrees are clean after commit. Earlier verification passed with `just check` in `sase` and `SASE_CORE_PATH=<local sase repo> just check` in `sase-github`.
