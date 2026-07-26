# Chat History - ace-run (chop.refresh_docs.sase.1_574131.1)

- **TIMESTAMP:** 2026-07-26 09:17:48 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** chop.refresh_docs.sase.1_574131.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.1_574131.1, tribe=chop)
Refresh the documentation for sase.

Review the current repository behavior and the changes since the last documentation
refresh. Update user-facing documentation so it is accurate, complete, and clear to
someone new to the project. You may only create, modify, or delete documentation
files, such as Markdown or other docs-tree content, READMEs, and doc-adjacent assets.
You MUST NOT create, modify, or delete source code, tests, build configuration, or any
other non-documentation file, even to fix a bug you are confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I’ll trace the most recent documentation-focused refresh in git history, compare all subsequent behavior changes against the current docs, then update only documentation and run the repo’s prescribed checks. I’ll also preserve any unrelated working-tree changes.

The prior broad refresh is commit `b0f491800` (`docs: refresh user-facing documentation`). I’m using that as the comparison point; there are about thirty commits after it, with the main user-facing additions appearing to be detached task management, raw xprompt inputs, the unified prompt-input panel, and agent-index repair. I’m now validating those against the actual CLI/TUI behavior rather than relying on commit subjects.

The existing task documentation already anticipates durable detached commands, but it currently describes `--session` attribution that the new detached-task API explicitly no longer records. The xprompt guide is also still centered on legacy `{N}` positional placeholders, while the current launch path turns raw placeholders into named input fields and preserves literal zones. I’m checking exact syntax, ordering, validation, and CLI behavior before editing those sections.

I found one real implementation gap that affects what the docs can honestly promise: the new raw-placeholder planner and unified modal exist, but the ACE launch path still constructs the modal with an empty placeholder list and never applies placeholder values. I’ll document the behavior users actually get—raw tags assist editing and are converted when saving xprompts, but ordinary launches preserve them—and call out the unwired collection path as a suspected code bug in the handoff. I’m also covering the new public detached-task API and the SDD concurrency/recovery safeguards.

The editable install is rebuilding the local Rust core so I can verify parser and placeholder behavior against the same binding the docs describe. No repository files have been changed yet.

The rebuild is still in the final native-extension stage. While it runs, the documentation scope is now four focused areas: prompt inputs/xprompt authoring, durable task APIs, SDD safety behavior, and built-in bead-agent priority. Existing agent-index, queued-clan, and bead-refresh docs already match their post-refresh commits.

The runtime probes confirmed the edge cases: raw placeholders are single-line `<…>` tags, repeated labels coalesce, inline/fenced code is protected, replacement values are not rescanned, and normal ACE launch still sends the tags literally. I’m applying documentation-only edits now; no generated memory/instruction files or runtime Markdown templates are in scope.

The documentation edits are in place and remain confined to `docs/`. I’m doing a claim-by-claim review now, including checking public function signatures and generated table formatting before running Markdown and strict MkDocs validation.

The first review corrected one overstatement: `origin` is a required argument for detached submissions, but the implementation does not reject an empty string. I also added the less-obvious raw-placeholder rule that HTML-like tags and angle-bracket link destinations are syntactically treated as placeholders unless they are in code zones. The edited files are now formatted, and only documentation is modified.

The content review is clean enough to validate. I’m starting the repository’s Markdown formatter check and strict MkDocs build in parallel; afterward I’ll run the mandatory full `just check` required for any non-exempt repository changes.

Both documentation checks passed: all Markdown matches Prettier, and the strict MkDocs site build completed successfully. I’m now running the required full repository check; this is broader than the documentation-specific validation and may take a few minutes.

The full check reached all formatting and lint stages successfully, then stopped at SASE validation because five installed/generated `sase_beads` provider skill files in the external chezmoi source are stale by 19 lines. That state predates and is outside this docs-only scope, so I’m not overwriting it. I’ll run the remaining check stages directly so the documentation change still gets the broadest available verification.

The remaining test stage is still running. Two failures have appeared among more than 22,000 tests; I’m letting the suite finish so I can inspect their exact causes and distinguish repository/environment failures from anything documentation-related.

The documentation-specific checks are clean. I’m finishing the broader repository verification now and separating any pre-existing or environment-level failures from this docs-only change.

The full suite left 25 failures across TUI rendering, agent-index/name-registry, sync, and suite-gate tests—far outside the edited docs. I’m rerunning just those failures once to distinguish persistent failures from parallel-suite flakes.

The rerun reduced the broad-suite failures to four persistent, clearly unrelated issues: an undefined test helper, an overlong Unix socket path, an existing forbidden import boundary, and a 95-pixel visual drift. I’ve left all code, tests, snapshots, and external provider files untouched as required.

Documentation refresh is complete. Only eight files under `docs/` changed.

Highlights:

- Documented current raw prompt-placeholder behavior and xprompt conversion rules in [xprompt.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/xprompt.md:621).
- Added durable detached-task kinds, APIs, visibility, filtering, and reconciliation details in [integrations.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/integrations.md:112) and [ace.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/ace.md:3238).
- Documented agent-index repair, SDD locking/retries, recovery snapshots, failure cooldowns, bead refresh modes, runner priorities, and terminal-smoke execution.
- No source, tests, build configuration, or snapshots were modified.

Checks:

- `just fmt-md-check` — passed
- `just docs-check` — passed
- `just validate-committed-plans` — passed
- `git diff --check` — passed
- `just check` — formatting and all lint stages passed, but validation stopped on five stale external chezmoi provider-skill files. They were not overwritten because they are outside this documentation-only scope.
- The test suite remains non-green due to four unrelated failures: an undefined `_family_root` test helper, an overlong Unix socket path, an existing `agents_sync` → ACE import-boundary violation, and a 95-pixel visual snapshot drift.

Suspected code bug left untouched: raw-placeholder extraction and substitution exist in [prompt_placeholder_inputs.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/agent/prompt_placeholder_inputs.py:48), but the ACE launch path creates a plan with `placeholders=()` and renders only declared inputs in [_launch_start.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/actions/agent_workflow/_launch_start.py:113). The docs therefore describe actual behavior: ordinary launches preserve raw `<label>` tags; xprompt conversion handles them.

I made the listed documentation changes, so I’m using the `sase_git_commit` workflow now to commit exactly those eight files and leave all unrelated/external state untouched.

The diff matches the completed refresh and is confined to the eight requested `docs/` files. I’m committing it as a documentation-only change with a message focused on the newly documented behavior.

The commit itself has been created (`0db56c1d1`), and the wrapper is still completing its synchronization/rebase phase against five newer upstream commits. I’m checking that final state before declaring it done.

The synchronization did pause on one real conflict in `docs/ace.md`; the other seven files replayed cleanly. I’m resolving that documentation conflict by preserving the newer upstream wording and integrating the refresh additions, then I’ll resume the wrapper so it can finish the push and bookkeeping.

The conflict is semantically resolved; the Markdown checker found only table wrapping in that merged section. I’m applying the repository formatter to `docs/ace.md`, then I’ll re-run the documentation checks before resuming the commit.

The rebased commit is now pushed as `63ce10cf0`. The wrapper reported only a deferred agent-hood publication warning (the primary commit succeeded); I’m removing its leftover temporary message file and verifying the repository is clean.

Committed and pushed the documentation refresh:

- Commit: `63ce10cf0 docs: refresh current user workflows`
- Exactly eight `docs/` files committed
- `just fmt-md-check` and `just docs-check` passed after rebase
- Working tree is clean and synchronized with `origin/master`

Suspected bug remains: ACE detects raw `<label>` placeholders but does not collect or substitute them during ordinary launches.

The commit wrapper also reported that agent-hood `lg` publication will retry automatically; the primary commit and push succeeded.
