# Chat History - ace-run (sase-ag.2)

- **TIMESTAMP:** 2026-07-28 10:08:44 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ag.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-ag, bead=sase-ag.2)
%model:@small_phase_worker
%auto
Can you complete the work for bead sase-ag.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Closing an assigned phase bead is unaffected by the parent-close
descendant guard. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

My phase is #2 (hosted-links). Let me explore the existing helpers.

Now I'll write the module.

Now factor the two existing branch resolvers onto the shared helper.

Now the agents_sync side:

Done. Bead `sase-ag.2` (hosted-links) is closed.

## What landed

**`src/sase/sdd/hosted_links.py`** (new) — local-only, never-raising GitHub URL resolution:

- `HostedLinkResolver.plan_url(plan_ref)` — normalizes a plan reference through `plan_refs.parse_plan_reference` (logical `plans:` refs rebase onto the store's plans root; legacy relative refs are already repo-relative; absolute refs must fall under the plans repo) and builds a blob URL via `github_blob_url`.
- `.agent_url(name)` — reuses `resolve_sync_targets` for the agents sidecar remote, `agent_link_target` for the path/anchor, and `hosted_provider` for GHE hosts.
- `.commit_url(sha)` — primary checkout's `origin` remote through `github_commit_url`.
- Each returns `None` rather than guessing when a remote, branch, or provider isn't authoritative, so callers render unlinked labels.
- `resolve_hosted_branch(repo, git_runner=...)` — the shared HEAD → `origin/HEAD` branch resolution.
- `hosted_link_resolver(...)` — process-level cache keyed by store repo root, project, and primary checkout; all three remote/branch lookups are memoized per instance so a tree-wide reconcile shells out a constant number of times.

**Factored out the two duplicate branch resolvers** as the plan required: `plan_paths._store_commit_branch` and `agents_sync/links.py` now delegate to `resolve_hosted_branch`; `_git_symbolic_ref` and `_sidecar_branch` are gone.

**`Justfile`** — `--epic-symbol 'sase-ag(HostedLinkResolver)'` / `'sase-ag(hosted_link_resolver)'`, since the consumers arrive in the `associations` and `write-points` phases.

**`tests/sdd/test_hosted_links.py`** — 14 tests covering logical/legacy/out-of-repo plan refs, the fallback cases (in-tree store, no remote, no branch, non-GitHub sidecar, malformed SHA, missing origin), the family-member agent anchor, and both caching guarantees (50 plan lookups → 1 git call; factory identity).

## Verification

`just check` passes fmt, keep-sorted, ruff, mypy, pyscripts, symvision, and toobig. Two things to flag:

- `sase validate` fails on `plan links validate` with `202607/prompts/plan_header_provenance.md: 'plan' target does not exist: ../plan_header_provenance.md`. I confirmed this is pre-existing by stashing my changes and re-running — the epic's own plan file was never committed to the plans sidecar. Not caused by this phase, and not mine to fix here.
- Full `just test`: 23,020 passed, 3 failed under parallel load (`test_kill_during_retry_wait_stops_before_another_subprocess`, `test_deep_archive_typing_burst_fetches_once_and_becomes_exact`, `test_concurrent_plan_file_launches_serialize_through_terminal_push`). All three pass when re-run serially and none touch hosted links — they look load-flaky.

I did not commit; no commit was requested. Nothing was written to the `sase--plans` sidecar, per the epic's constraint.

Bead is closed. Now committing.

Committed and pushed — working tree clean, `master` level with `origin/master`.

**Commit `563deafc5`** — `feat(sdd): add hosted URL resolution for plans, agents, and commits (sase-ag.2)`, covering all five files:

- `src/sase/sdd/hosted_links.py` (new) — `HostedLinkResolver` with `plan_url` / `agent_url` / `commit_url`, each returning `None` rather than guessing; `resolve_hosted_branch` shared helper; `hosted_link_resolver()` process-level cache with per-instance memoized remote/branch lookups.
- `src/sase/workflows/commit/plan_paths.py`, `src/sase/agents_sync/links.py` — duplicate branch resolvers factored onto `resolve_hosted_branch`.
- `Justfile` — epic-symbol whitelist for the two new symbols (consumers land in phases 3/4).
- `tests/sdd/test_hosted_links.py` (new) — 14 tests.

Bead `sase-ag.2` was already closed before the commit; the wrapper's idempotent re-close is a no-op. Parent epic `sase-ag` untouched.

One warning from the commit: the project has 3 quarantined agent-hood publication requests, so the agent link written into this commit may not resolve until `sase agent sync --retry-quarantined` runs. That's a pre-existing outbox backlog, not something this commit introduced — I haven't run the retry since you didn't ask.
