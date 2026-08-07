# Chat History - ace-run (chop.refresh_docs.sase.9_687614.2)

- **TIMESTAMP:** 2026-08-06 03:31:40 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.9_687614.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.9_687614.2, tribe=chop)
%wait:chop.refresh_docs.sase.9_687614.1
%wait(runners=0)
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where terminology or
workflow ordering could be misunderstood. You may only create, modify, or delete
documentation files, such as Markdown or other docs-tree content, READMEs, and
doc-adjacent assets. You MUST NOT create, modify, or delete source code, tests, build
configuration, or any other non-documentation file, even to fix a bug you are
confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I'll start by looking at the documentation changes made by the update agent.

Now the marker-exclusion paragraph, where the stated marker expression and the listed markers could look contradictory:

Now the launch-preparation bullet (so `workspace.md`'s "how to recover by hand" pointer actually pays off) and the duplicate-ID section:

Now let me run the documentation checks.

All of the update agent's changed claims check out against the code, with three exceptions I corrected. Everything below was verified by reading the implementation, not by trusting the prose.

## Verified accurate (unchanged in substance)

- **beads.md — Publication Verification**: the post-push verify pass (`bead_store_mutation` → `ensure_bead_mutation_published`), the exact diagnostic text (`_sync_diagnostics.bead_publication_failure_lines`), `--no-push` skipping it, the swallow-on-exception behavior, and both other enforcement surfaces.
- **commit_workflows.md**: `chore(beads): sync bead state`, `status=failed` / `reason=bead_state_unpublished`, failure held until the finalizer's return points, diagnostic appended on the dirty-after-max-passes path.
- **workspace.md / beads.md**: `workspace_num > 1` eviction guard, synchronous publish, recovery ref, `sase/repos` → `.sase/trash` rename.
- **plugins.md**: lock and holder paths, both message forms verbatim, blocking vs. advisory holders, `SASE_DISABLE_CODE_SWAP_LOCK=1`, the residual race.
- **agent_families.md**: `MODEL_LANE_LIMIT = 12`, the `default` fallback, the overflow tail string, `--<suffix>` labels shared with the `FAMILY MEMBERS` roster.
- **configuration.md**: path-beats-name resolution in `match_repo_record` and the `<kind> '<name>' (<path>)` candidate format.
- **development.md**: contract manifest as a generated projection, the drift test, the normalized-CPU budget guard, `contract-set-only` not escalating, `selection-tooling` escalating.

## Corrections (docs disagreed with code)

- **plugins.md** claimed a blocked `sase update` "reports its outcome as deferred." The outcome status is `failed` with a reason string starting `deferred:`, and `dev_update_succeeded()` returning false makes the command **exit non-zero**. Documented that.
- **development.md:236** still said "The coverage recipe … includes the visual regression tests" — stale since `9672c5602`, and directly contradicted by the paragraph the update agent fixed 30 lines later. Rewritten to preserve the historical measurement while stating current behavior.
- **configuration.md:42** had a dead TOC link to `#chat_history`; no such heading or config key exists (schema has only `chat_install`). Surfaced by `just docs-check`, now removed.

## Clarity fixes

- **agent_families.md**: the new `#### Per-member model lanes` heading had been inserted mid-narrative, so the following "also follows that two-position scale" paragraphs (SLOW TOOL CALLS, prompt sections, NEIGHBORS) ended up nested under it and orphaned from the fold-level discussion they refer back to. Moved the subsection to the end of *Family detail folding* and noted the lanes are outside the fold scale.
- **development.md**: "excludes the `slow`, `visual`, and `terminal_smoke` markers" read as contradicting the stated `not slow and not visual` expression; the smoke tests are excluded because they also carry `slow`. Also documented the workflow-ordering trap a new user will hit: both manifest guards live *outside* the contract set, so a marked-but-not-regenerated module passes `just check` and only fails under `just check-full`/CI.
- **beads.md**: "read-only mount" → the actual concept (a store discovered through a checkout-local `.sase/sdd-store.json` record, which refuses mutations outright); added the sync-log location (`~/.sase/bead_push_logs/sync-*.log`) so "check the sync log" is actionable; added the `refs/sase/recovery/` namespace so workspace.md's "how to recover by hand" pointer pays off; dropped the "now relocates" framing.
- **configuration.md**: made clear the record path must be copied exactly as printed and is a disambiguator, not an "open any directory" mode.

## Suspected code bug (not fixed)

`src/sase/dev_update/code_swap_lock.py:363` maps the holder op `dev.update` to the display string **`sase dev update`**, and `src/sase/bead/cli_work_entry.py:348` opens its refusal with the same name. There is no `sase dev` subcommand — the user-facing command is `sase update` (`dev` is only a value of `sase update -t/--to`, and `dev_update` an internal module name). The sibling message at `src/sase/dev_update/execute.py:100` says `sase update` correctly. So a user blocked by a swap is told to wait for a command they cannot find. The same stale name appears in docstrings/comments at `code_swap_lock.py:3,92,143`, `axe/run_agent_runner.py:71`, `axe/run_agent_exec_plan_accept.py:333`, `axe/run_agent_runner_launch.py:223,227`, and `axe/source_skew.py:1`. I left the docs quoting only the correct messages and did not touch any code.

Checks run: `just fmt-md-check` and `just docs-check` (mkdocs `--strict`) both clean, plus a full `just check` — all twelve gates green, scoped lane included. Changes are staged in the working tree only; I have not committed.

These are my review edits on top of the update agent's committed refresh (`531138373`). Committing them now.

Committed as `a7e6f0514`; working tree clean and level with `origin/master`.

## What the commit contains

Review of the update agent's docs refresh (`531138373`), with every changed claim checked against the implementation.

**Corrections where docs disagreed with code:**
- `plugins.md` — a lock-blocked `sase update` reports status `failed` with a reason beginning `deferred:` and exits non-zero; it does not report an outcome of "deferred."
- `development.md:236` — "the coverage recipe … includes the visual regression tests" was stale since `9672c5602` and contradicted a paragraph 30 lines later.
- `configuration.md:42` — dead TOC link to `#chat_history` (no such heading or config key; schema has only `chat_install`). Caught by `just docs-check`.

**Clarity fixes:** moved the new per-member-model-lanes subsection out of the middle of the fold-scale narrative in `agent_families.md`; explained in `development.md` that `terminal_smoke` tests are excluded by `not slow and not visual` because they also carry `slow`, and documented that both contract-manifest guards live outside the contract set (so a marked-but-not-regenerated module passes `just check` and fails only under `just check-full`/CI); replaced `beads.md`'s invented "read-only mount" with the real concept and added the sync-log path and `refs/sase/recovery/` namespace so its pointers are actionable; clarified in `configuration.md` that a candidate record path is a disambiguator, not an "open any directory" mode.

**Verified accurate and left alone:** the publication-verification flow and diagnostics in `beads.md`, the `chore(beads): sync bead state` / `reason=bead_state_unpublished` details in `commit_workflows.md`, the `workspace_num > 1` eviction guard, the lock/holder paths and `SASE_DISABLE_CODE_SWAP_LOCK=1`, `MODEL_LANE_LIMIT = 12`, and the contract-manifest drift test and CPU budget guard.

## Suspected code bug (not fixed, per scope)

`src/sase/dev_update/code_swap_lock.py:363` maps the `dev.update` holder op to the display string **`sase dev update`**, and the refusal in `src/sase/bead/cli_work_entry.py:348` opens with the same name. There is no `sase dev` subcommand — the user-facing command is `sase update` (`dev` is only a value of `-t/--to`), and the sibling message at `src/sase/dev_update/execute.py:100` gets it right. A blocked user is told to wait for a command they can't find. The stale name also appears in comments/docstrings at `code_swap_lock.py:3,92,143`, `axe/run_agent_runner.py:71`, `axe/run_agent_exec_plan_accept.py:333`, `axe/run_agent_runner_launch.py:223,227`, and `axe/source_skew.py:1`. It's noted in the commit body; the docs quote only the correct message.

Checks: `just fmt-md-check` and `just docs-check` (mkdocs `--strict`) clean, and a full `just check` green across all twelve gates. The commit's `just fix` pre-hook made no further changes.
