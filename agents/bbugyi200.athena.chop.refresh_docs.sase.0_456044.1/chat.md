# Chat History - ace-run (chop.refresh_docs.sase.0_456044.1)

- **TIMESTAMP:** 2026-07-29 02:04:39 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** chop.refresh_docs.sase.0_456044.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.0_456044.1, tribe=chop)
%wait(runners=0)
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

I’ll trace the repository history to identify the last documentation-focused refresh, compare subsequent behavior changes against the current docs, then update only documentation and run the repo’s documentation checks (plus the mandated validation for changed files).

The latest broad refresh appears to be the July 26 pair (`refresh current user workflows` followed by `align operational guidance`); later documentation commits are feature-specific. I’m using that pair as the baseline and will account for all behavior changes after it, including features that received partial docs.

I found a concrete stale path model in the main SDD guide: several sections still say split-layout beads live inside `--plans`, while current schema-3 projects use the dedicated `--beads` repository. I’m checking the adjacent command/lifecycle guidance now so the correction is consistent rather than a one-line patch.

The path mismatch is broader than the SDD page: architecture, workspace, integration, configuration, Rust-backend, development, and the Beads/SDD article still present the legacy schema-2 `--plans/beads` layout as the only split layout. I’ll update those references to distinguish current schema-3 projects from unmigrated compatibility stores.

The launch audit uncovered another behavioral change from the latest bead work: `sase bead work` now writes and synchronously publishes one pre-spawn checkpoint containing readiness plus all phase/land assignments. The old post-launch `bead.push_after_commit` path is no longer consulted, so I’m correcting the lifecycle and configuration prose to match that behavior, including the `--no-push` limitation for detached stores.

The documentation now covers the newly surfaced behavior and remains docs-only. I’m moving into validation: first refreshing the workspace’s editable install as required by this repository, then running the strict HTML/PDF/deploy documentation checks and the full mandated check suite.

The install is still compiling the workspace-matched Rust extension; no validation failure has appeared. The docs diff remains limited to Markdown under `docs/`.

The strict HTML build passed. The PDF build has rendered and post-processed the 42-chapter handbook successfully; its final validator is still running.

The full check reached repository validation and stopped on pre-existing deployed-skill drift outside this checkout: `sase init skills --check` wants to overwrite 15 files in the chezmoi-managed home tree. I won’t alter those non-documentation files under this task’s scope. The repository-local validation legs passed, and I’m running the remaining committed-plan and test legs separately so this external drift does not hide any docs-related failure.

The full test suite is in its final stretch. After it finishes, I’ll do one last scope and whitespace audit so the handoff clearly separates repository validation from the unrelated external skill drift.

Documentation refresh complete. Updated 13 Markdown files covering:

- Dedicated schema-3 beads sidecar storage and legacy compatibility.
- Current `sase bead work` checkpoint, publication, rollback, and failure behavior.
- Plan-header bead provenance.
- Agent publication retirement and `sase agent sync --drop-retired`.
- Registry-backed project xprompt discovery.
- CLI, configuration, architecture, workspace, integration, development, and onboarding guidance.

All modifications are documentation-only: 250 insertions and 226 deletions.

Validation:

- `just docs-check` — passed
- `just docs-pdf-check` — passed
- `just docs-deploy-artifact-check` — passed
- `just validate-committed-plans` — passed
- `just test` — 23,327 passed, 7 skipped
- `git diff --check` — passed
- `just check` — repository checks passed until `sase init skills --check`, which found pre-existing drift in 15 generated skill files under `~/.local/share/chezmoi`. Those external, non-documentation files were left untouched.

Suspected implementation issue: `tools/check_bead_store_soak` still checks the legacy `plans/beads/issues.jsonl` path. Schema-3 projects use the dedicated beads sidecar, so `just test-bead-store-soak` currently misses the active store and can fail with a missing-file error. I documented that limitation in [development.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/development.md). The exposed `bead.push_after_commit` configuration also appears to have no current code consumer.

The documentation work is complete and the listed changes are from this session. The commit finalizer therefore requires me to use the `sase_git_commit` workflow now, with each of the 13 documentation files explicitly scoped.

The scoped diff contains only the intended documentation refresh: schema-3 bead storage, the current bead-work launch checkpoint, plan/bead provenance, retired publication handling, and registry-backed xprompt discovery. I’m preparing a documentation-only conventional commit; the known soak-check implementation mismatch will be described in the commit body without touching code.

Committed the documentation refresh as `791dec5ca` (`docs: refresh current user workflows`).

- Updated 13 documentation files; no source, test, or configuration files changed.
- Documentation checks passed, including HTML, PDF, and deployment-artifact validation.
- Full tests passed: 23,327 passed, 7 skipped.
- Working tree is clean and synchronized.

Suspected implementation issues left untouched:

- `tools/check_bead_store_soak` still targets legacy `plans/beads/issues.jsonl`, missing schema-3 bead sidecars.
- `bead.push_after_commit` appears to have no current code consumer.
- `just check` encountered pre-existing drift in 15 externally generated chezmoi skill files.
