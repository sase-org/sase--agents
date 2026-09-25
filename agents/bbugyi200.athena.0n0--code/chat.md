# Chat History - ace-run (0n0--code)

- **TIMESTAMP:** 2026-09-18 14:12:02 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 0n0--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202609/agent_node_refresh_isolation.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll implement the approved plan from the plans sidecar. First I'm loading the execute-plan and repo skills, then I'll open the sidecar and read the plan.

The execute-plan skill is loaded. Next I’ll open the plans sidecar, read the approved plan, and pull in SASE finalizer and related skills.

I'll open the plans sidecar and read the approved plan, then start implementation from that.

This is an approved SASE tale plan, not a multi-PR DAG. I’ll pull the cited prior work and the current TUI loading/ownership code, then implement the isolation fix.

I’ve got the plan and prior epic context. Next I’ll map the snapshot/worker pipeline and the existing tests so the isolation boundary is placed correctly.

I have a clear ownership boundary: cheap UI snapshots stay as they are, and the worker gets a detached graph before any mutation. Next I’ll add that copy/ownership layer and the regression tests.

Isolation tests passed. Next I’ll update the identity-based assertions and inspect the panel rebuild failure.

Implemented worker/UI isolation for Agents-tab row graphs on source revision `e0f1a8d43` (the same tree the plan diagnosed). Cached `Agent` objects are no longer shared across the worker/UI boundary.

**What changed.** `_make_prepared_apply_snapshot` still does a cheap list capture for stale-token checks. Before any mutating prepare (incomplete merge, status overrides, `sort_and_reorder`, slot annotation, proc-shell carryover), `own_prepared_apply_snapshot` copies the reachable row graph with a shared memo. Incoming loader rows stay worker-owned; live cached rows are replaced by copies. `frozen=True` on the snapshot dataclass is documented as not isolating the mutable rows it holds.

**Race coverage.** A clan in `@epic` with Claude + Codex members, and a multi-provider family, keep their provider order, child links, family classification, status, and counts while relationship normalization is paused, after the worker finishes, and if the worker raises or is abandoned. Ten unrelated exact-delta prepares leave the live prefix unchanged. Legitimate additions, deletions, and dismissals still appear on apply.

**Cost.** On an 80-row graph with shared family back-pointers: one copy of 80 unique objects in **14.2 ms** on the worker thread; a repeated 3-row copy against the same memo was **0.003 ms**. Copying stays off the event loop on async refreshes.

**Checks.** Lint (`just check` gates through symvision/toobig) passed. Focused isolation, merge, apply-boundary, fold, and BY_STATUS panel tests passed. The scoped `just check` lane escalated to the full suite: **4505 passed**. The **3 failures** are unrelated `sase_core_rs` binding `select_remaining_commit_obligations` (installed wheel vs unpublished core capability); they are not in this change.

**Live TUI limit.** This was a disposable workspace clone, not the user’s live session. Proof is controlled replay (thread barriers + ten prepares + BY_STATUS panel identity), not a live athena soak.
