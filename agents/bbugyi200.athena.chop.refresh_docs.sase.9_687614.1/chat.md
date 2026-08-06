# Chat History - ace-run (chop.refresh_docs.sase.9_687614.1)

- **TIMESTAMP:** 2026-08-06 02:41:35 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.9_687614.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.9_687614.1, tribe=chop)
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

I'll start by understanding the repository's documentation structure and what's changed since the last docs refresh.

Now let me make the documentation updates. Starting with `docs/development.md`:

Now the contract-set documentation:

Now fix the stale remediation advice in the Selection Health section:

Now `docs/plugins.md` — the code-swap lock:

Now `docs/agent_families.md` — per-member Model lanes:

Now `docs/beads.md` — publication verification and duplicate-ID recovery:

Now add the publication-verification section under Sync Mechanism:

Now update the beads table of contents:

Now the commit finalizer flow in `docs/commit_workflows.md`:

Now `docs/workspace.md` — the eviction refusal:

Now let me run the documentation checks:

Now let me run the full `just check` since I changed files:

Documentation refresh complete. All checks pass (`just check` green, `just docs-check` exit 0, prettier clean).

## What I reviewed

118 commits since the last refresh (`39ef28e01`, 2026-08-02). Most user-facing work in that range was already documented incrementally — bead close history/reopen provenance, bead creation-time presentation, model alias defaults, timezone rendering, inline sidecar publication, and the agent-CLI update history panel all landed with their doc updates. I focused on the commits that changed behavior but touched no docs, plus one stale claim.

## Changes (docs only)

**`docs/development.md`** — Corrected a stale claim that default test runs *include* the ACE PNG snapshot tests; `just test`, `just test-cov`, and `just test-scoped` all exclude `visual` since `9672c5602`. Added a **contract set** subsection: `tests/contract_manifest.txt` is generated from `@pytest.mark.contract` (not hand-maintained), regenerated with `just refresh-contract-manifest`, guarded by a normalized CPU budget, and is itself a broadening rule. Also documented the `contract-set-only` floor — a docs-only change runs exactly the contract set and does *not* escalate. Fixed the Selection Health remediation advice, which told readers to hand-edit the generated manifest. I verified the `contract-set-only` claim against this very change: `tools/select_tests --explain` reported 34 of 2316 files, rules `contract-set-always, contract-set-only`.

**`docs/plugins.md`** — New "code-swap lock" subsection. This mechanism was entirely undocumented: `sase bead work` takes a blocking shared lock that defers a dev update, while agent runners register as *advisory* holders that only produce a warning and can never block a swap. Covers lock paths, both message forms, `SASE_DISABLE_CODE_SWAP_LOCK=1`, and the accepted residual race.

**`docs/beads.md`** — Two new subsections under Sync Mechanism. **Publication Verification**: bead CLI mutations now force a synchronous push and re-verify, failing with an operator diagnostic when a commit stays local, plus the two other surfaces enforcing the same invariant (commit finalizer, launch-time workspace prep). **Duplicate Bead IDs**: concurrent clones minting the same ID are now resolved by relocation rather than wedging the store, reporting `relocated duplicate beads: <old> -> <new>`.

**`docs/commit_workflows.md`** — Added the finalizer's bead-state safety net and its `status=failed` / `reason=bead_state_unpublished` outcome to the flow.

**`docs/workspace.md`** — Documented that launch preparation of workspace `#2`+ refuses eviction when sidecar bead clones hold unpublished commits.

**`docs/agent_families.md`** — New "Per-member model lanes" subsection for the family detail panel's expanded `Model:` field (12-lane cap, `default` fallback, overflow tail).

**`docs/configuration.md`** — `sase repo open` now documents that ambiguous names can be disambiguated by passing a listed record path.

## Suspected code issue (not fixed, per scope)

`sase bead work`'s code-swap error text says *"sase dev update is swapping the installed source tree"* (`src/sase/bead/cli_work_entry.py:348`). There is no `sase dev` subcommand — the user-facing command is `sase update`, and `dev_update` is only the internal module name for its editable path. The sibling message in `src/sase/dev_update/execute.py:100` correctly says `re-run \`sase update\``. The docstring at `src/sase/dev_update/code_swap_lock.py:3` carries the same stale name. I documented the actual behavior rather than the misleading string.

These are my changes from this session. Committing them now.

The plugins.md diff shows a prettier-mangled passage with broken inline code spans. Let me fix that before committing.

Rewriting the mangled bullet so the message strings render correctly.

Line 274's zero-indent continuation is ugly. Restructuring so the ACE message also gets its own block.

My bare `npx prettier` used default settings; the repo uses `--prose-wrap=always --print-width=120`. That's what mangled the file. Reformatting correctly.

Only the seven docs files are modified. Running the full check gate.

All green. Writing the commit message and committing.

Committed and pushed. Working tree clean, branch level with `origin/master`.

## Commit

`531138373 docs: refresh user-facing documentation` — 7 files, docs only.

## What changed

I reviewed the 118 commits since the last docs refresh (`39ef28e01`, 2026-08-02). Most user-facing work in that range had already landed with its own doc updates; I covered the commits that changed behavior without touching docs, plus one stale claim.

- **`docs/development.md`** — Corrected a stale claim that default test runs *include* the ACE PNG snapshot tests; `just test`, `just test-cov`, and `just test-scoped` have all excluded `visual` since `9672c5602`. Added a contract-set subsection: `tests/contract_manifest.txt` is generated from `@pytest.mark.contract`, regenerated via `just refresh-contract-manifest`, guarded by a normalized CPU budget, and is itself a broadening rule. Documented the `contract-set-only` floor (a docs-only change runs exactly the contract set and does not escalate) — verified against this change: `tools/select_tests --explain` reported 34 of 2316 files, rules `contract-set-always, contract-set-only`. Fixed Selection Health remediation advice that told readers to hand-edit the generated manifest.
- **`docs/plugins.md`** — New code-swap lock section, previously undocumented: blocking readers (`sase bead work`) versus advisory agent-runner holders that only warn, lock paths, both message forms, `SASE_DISABLE_CODE_SWAP_LOCK=1`, and the accepted residual race.
- **`docs/beads.md`** — Publication Verification (forced synchronous push and re-verify after bead CLI mutations, the operator diagnostic, and the two other surfaces enforcing the invariant) and Duplicate Bead IDs (relocation-based resolution of concurrently minted IDs).
- **`docs/commit_workflows.md`** — The finalizer's bead-state safety net and its `status=failed` / `reason=bead_state_unpublished` outcome.
- **`docs/workspace.md`** — Launch prep of workspace `#2`+ refuses eviction when sidecar bead clones hold unpublished commits.
- **`docs/agent_families.md`** — Per-member `Model:` lanes in the family detail panel (12-lane cap, `default` fallback, overflow tail).
- **`docs/configuration.md`** — Ambiguous `sase repo open` names can be disambiguated by passing a listed record path.

One correction to my earlier report: I'd said prettier was clean, but the check I ran used bare `npx prettier` defaults rather than the repo's `--prose-wrap=always --print-width=120`, which had mangled a passage in `docs/plugins.md` into broken inline code spans. I rewrote that passage using fenced blocks for the two message strings and reformatted via `just fmt-md`. `just check` is green (all 12 gates, including `fmt (markdown)` and `test (scoped)`) and `just docs-check` exits 0.

## Suspected code issue (not fixed, per scope)

`sase bead work`'s code-swap error text says *"sase dev update is swapping the installed source tree"* (`src/sase/bead/cli_work_entry.py:348`). There is no `sase dev` subcommand — the user-facing command is `sase update`, and `dev_update` is only the internal module name for its editable path. The sibling message at `src/sase/dev_update/execute.py:100` correctly says `re-run \`sase update\``, and the docstring at `src/sase/dev_update/code_swap_lock.py:3` carries the same stale name. I documented the actual behavior rather than the misleading string; this is also noted in the commit message body.
