# Chat History - ace-run (sase-1qz.6.1.4--plan)

- **TIMESTAMP:** 2026-11-04 17:15:15 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1qz.6.1.4--plan

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: j53tjym307rn
Inspect with: sase monitor show j53tjym307rn
Monitor turn: sase-1qz.6.1.4--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20

Command:

```sh
sase tool run check
```

Reason:

finish check for bead sase-1qz.6.1.4 (resolution_launch)

Next action:

The joined run is `just check` for bead sase-1qz.6.1.4 (Exactly-once recovery launch and settlement). If the run passed, close ONLY bead sase-1qz.6.1.4 with: sase bead close sase-1qz.6.1.4 --note "resolution_launch: recover.* CAS transaction, strict-spawn dispatch, ack confirmation, idempotent done.json settlement; 60 new tests pass; just check green; epic-symbols for 1.4 removed". Do NOT close the parent epic, any ancestor bead, or any other bead. Before closing, run sase bead epic-symbols sase-1qz.6.1.4 and confirm no 1.4 entries remain. If the run failed, do NOT close the bead: report which stage failed and leave the bead open.


## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-1qz.6.1, bead=sase-1qz.6.1.4)
%model:@medium
%auto
%w(sase-1qz.6.1.2, for_epic=false)
%w(bead=sase-1qz.6.1.2)
%w(bead=sase-1qz.6.1.3)
Can you complete the work for bead sase-1qz.6.1.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1qz.6.1.4` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything, and run `sase bead open sase-1qz.6.1.4` only if the work
is genuinely unfinished. Read its
description and design file with `sase bead read sase-1qz.6.1.4 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1qz.6.1.4 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1qz.6.1.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1qz.6.1.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Phase `sase-1qz.6.1.4` (resolution_launch) is implemented; the bead stays open pending the joined `just check` run.

**Built** — exactly-once recovery transaction in six focused modules under [src/sase/agent/hijack/](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/):
- [recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover.py) — `recover_hijacked_agent` orchestration: fresh-preview validation, CAS held→resolving with full reservation (action, reserved name, concrete target, resolver identity, launch/admission binding), binding persisted via `record_launch` before dispatch, pinned-target revalidation, strict-seam dispatch, confirm-and-settle.
- [recover_settle.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_settle.py) — idempotent `settle_recovery` (CAS + `done.json` with outcome preserved, ESCALATED/CONTINUED via the existing Rust mapping) plus inheritance evidence gathering.
- [recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_target.py), [recover_subject.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_subject.py), [recover_confirm.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_confirm.py), [recover_common.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_common.py) — target resolution (Continue pins predecessor concrete; Instruct `-m` > `%model:` > default; launch/fan-out conflicts refuse), subject loading, post-spawn confirmation (identity, claim, ack, model; rollback + terminate on failure, uncertain otherwise).

**Tests** — 60 passing: [test_agent_hijack_recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover.py) (transaction order, repeat/concurrent resolvers, queued/error/uncertain, inheritance failure → held + terminated, settlement repair) and [test_agent_hijack_recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover_target.py).

**Gates** — ruff, mypy, fmt, symvision clean; the four `sase-1qz.6.1.4` epic-symbol rows removed from the local Justfile (they now have a real production caller).

**Pending** — full `just check` (run `30dad66b…`) was still in its test lane under heavy host load, so I joined it to monitor `j53tjy` with a verify follow-up instructed to close only this bead on green (after re-checking epic-symbols) and report otherwise. A status note is on the bead.Done with the work, with one honest exception: the bead itself stays open, blocked by the close guard — details below.

## What was built (phase `sase-1qz.6.1.4`, resolution_launch)

Six focused modules under [src/sase/agent/hijack/](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/) (split because the first draft hit 2148 lines vs the 1000-line toobig hard gate):

- [recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover.py) — `recover_hijacked_agent` orchestrator: fresh-preview validation, CAS held→resolving with the complete reservation, admission binding persisted via `record_launch` before dispatch, pinned-target revalidation, strict-seam dispatch, confirm-and-settle. Repeat calls return the current resolution; losers of a CAS race return the winner's resolution without launching.
- [recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_target.py) — Continue pins the predecessor concrete target; Escalate pins the previewed target; Instruct requires the full edited prompt with explicit `-m` > `%model:` > Continue default, and refuses conflicting launch/fan-out directives.
- [recover_subject.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_subject.py), [recover_common.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_common.py) — record loading, session-base resolution, lineage (`{hijack_id, from_rung, to_rung, predecessor}` with concrete-model rungs), shared result/error types.
- [recover_settle.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_settle.py) — idempotent `settle_recovery` plus inheritance-evidence gathering. Settlement refuses before the CAS when the predecessor outcome is no longer hijacked.
- [recover_confirm.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_confirm.py) — post-spawn confirmation (successor identity, workspace claim, ack, model); definite failures roll back, terminate, and return to held; uncertain outcomes retain resolving for reconcile (phase 1.5).
- [__init__.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/__init__.py) exports the new public API — this gives the four 1.4-whitelisted symbols a real production caller.

Failure semantics: definite pre-launch failure → held with error, no duplicate; WorkspaceClaimError → queued (custody holds the claim); post-spawn uncertainty → resolving retained with diagnostic.

## Verification (all observed, not inferred)

- 60 new tests pass: [test_agent_hijack_recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover.py) + [test_agent_hijack_recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover_target.py) (fake-ledger CAS covering two-resolver races, repeat calls, queued/error/uncertain paths, inheritance-failure termination, idempotent settlement, ESCALATED/CONTINUED mapping through the real Rust binding).
- `just check` run `30dad66` (20m47s): every lint gate green (ruff, mypy, symvision, fmt, flags, pyscripts, waits, changelog, terminology, docs); scoped lane 60041 passed with 3 failures triaged KNOWN (witness `f07f3fe8c21a8203bed7ecbdbdafc7b1`, artifact-marker audit + agents-sync publication) and FLAKY — verdict `no_new_failures`, all unrelated to hijack recovery.
- Local 1.4 epic-symbol rows removed from the Justfile; symvision passes with the exact gate invocation.

## Why the bead is still open

`sase bead close` refuses: the four 1.4 rows still exist on `origin/master` (added by 1.3's commit; the guard unions local + default-branch rows by design). Re-keying locally cannot clear upstream keys, and the symbols are genuinely consumed, so there is nothing left to wire up. This matches the 1.2 precedent (commit 05:14, close 20:25 — land-then-close). A bead note records the full verification evidence and instructs the follow-up/land agent (1.7) to close this bead once the tree lands and the upstream rows clear. No task beads were created; no other beads touched; the staged verify monitor's follow-up will find the run green and the note.## Phase `sase-1qz.6.1.4` (resolution_launch) — work complete and verified; bead left open by the close guard

### What was built

Exactly-once keep-work recovery launch and settlement, in six focused modules under [src/sase/agent/hijack/](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/) (split from a 2148-line draft to respect the 1000-line toobig gate):

- [recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover.py) — `recover_hijacked_agent`: fresh-preview validation, CAS held→resolving with the complete reservation (action, reserved successor, concrete target, resolver identity, durable launch + admission identity), binding persisted via `record_launch` before dispatch, pinned-target revalidation, strict-seam dispatch, confirm-and-settle. Repeat calls and CAS-race losers return the current resolution without relaunching.
- [recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_target.py) — Continue pins the predecessor concrete target; Escalate pins the previewed target; Instruct precedence is explicit `-m` > edited `%model:` > Continue default, with conflicting launch/fan-out directives refused.
- [recover_subject.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_subject.py) / [recover_common.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_common.py) — record loading, session-base resolution, lineage (`{hijack_id, from_rung, to_rung, predecessor}`), shared result/error types.
- [recover_settle.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_settle.py) — idempotent `settle_recovery` (CAS + `done.json` with `outcome: hijacked` preserved, ESCALATED/CONTINUED via the existing Rust mapping; refuses before the CAS if the predecessor finished first) plus inheritance-evidence gathering.
- [recover_confirm.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_confirm.py) — post-spawn confirmation of successor identity, workspace claim, ack, and model; definite failures roll back, terminate, and return to held; uncertain outcomes retain resolving for reconcile.
- [__init__.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/__init__.py) re-exports the API — giving all four 1.4-whitelisted symbols a real production caller.

### Verification (observed)

- 60 new tests pass: [test_agent_hijack_recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover.py) (fake-ledger CAS: reservation order, binding-before-dispatch, two-resolver races, repeat calls, queued/error/uncertain, inheritance-failure termination, settlement + repair) and [test_agent_hijack_recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover_target.py).
- `just check` run `30dad66` (20m47s): all lint gates green (ruff, mypy, symvision, fmt, flags, pyscripts, waits, changelog, terminology, docs); scoped lane 60041 passed, 3 failed — all triaged KNOWN (witness `f07f3fe8c21a8203bed7ecbdbdafc7b1`) or FLAKY in unrelated areas, verdict `no_new_failures`.
- Local 1.4 epic-symbol rows removed; symvision passes with the exact gate invocation.

### Why the bead is not closed

`sase bead close` was retried and refuses solely on the four `origin/master` rows for the already-consumed symbols. I deliberately did **not** re-key: every symbol is resolved (the instruction's first alternative is satisfied), and re-keying cannot clear upstream keys from the guard's local+upstream union — it would only misattribute ownership and block a sibling phase later. The rows clear when this tree lands (the 1.2 precedent: commit 05:14, close 20:25); the staged verify monitor inherits the workspace for landing, and three bead notes record the evidence, the blocker, and this reasoning for the follow-up/land agent.## Phase `sase-1qz.6.1.4` (resolution_launch) — implementation and verification complete; bead close blocked by upstream rows pending land

### What was built

Exactly-once keep-work recovery launch and settlement, in six focused modules under [src/sase/agent/hijack/](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/) (split from a 2148-line draft to respect the 1000-line toobig hard gate):

- [recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover.py) — `recover_hijacked_agent`: fresh-preview validation, CAS held→resolving with the complete reservation (action, reserved successor name, concrete target, resolver identity, durable launch + admission identity), admission binding persisted via `record_launch` before dispatch, pinned-target revalidation, strict-seam dispatch, confirm-and-settle. Repeat calls and CAS-race losers get the current resolution without relaunching.
- [recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_target.py) — Continue pins the predecessor concrete target; Escalate pins the previewed target; Instruct precedence is explicit `-m` > edited `%model:` > Continue default, with conflicting launch/fan-out directives refused.
- [recover_subject.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_subject.py) / [recover_common.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_common.py) — record loading, session-base resolution, lineage (`{hijack_id, from_rung, to_rung, predecessor}`), shared result/error types.
- [recover_settle.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_settle.py) — idempotent `settle_recovery` (CAS + `done.json` with `outcome: hijacked` preserved, ESCALATED/CONTINUED via the existing Rust mapping; refuses before the CAS if the predecessor finished first) plus inheritance-evidence gathering.
- [recover_confirm.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_confirm.py) — post-spawn confirmation of successor identity, workspace claim, ack, and model; definite failures roll back, terminate, and return to held; uncertain outcomes retain resolving for reconcile (phase 1.5).
- [__init__.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/__init__.py) re-exports the API, giving all four 1.4-whitelisted symbols a real production caller; the four local Justfile exemption rows were removed.

### Verification (observed, not inferred)

- 60 new tests pass: [test_agent_hijack_recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover.py) (fake-ledger CAS: reservation order, binding-before-dispatch, concurrent-resolver single winner, repeat calls, queued/error/uncertain paths, inheritance-failure termination, settlement + repair) and [test_agent_hijack_recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover_target.py).
- `just check` run `30dad66` (20m47s): every lint gate green (ruff, mypy, symvision, fmt, flags, pyscripts, waits, changelog, terminology, docs); scoped lane 60041 passed, 3 failed — all triaged KNOWN (witness `f07f3fe8c21a8203bed7ecbdbdafc7b1`, artifact-marker audit + agents-sync publication) or FLAKY in unrelated areas, verdict `no_new_failures`.
- `sase bead epic-symbols`: no local 1.4 rows remain.

### On the close instruction (re-key, verify, retry)

Retried `sase bead close` — refused on the same four `origin/master` rows. I did **not** re-key, for three verifiable reasons, recorded in bead note #3:

1. The instruction's own disjunction is already satisfied the other way: every symbol is **resolved** — all four have a real production caller in `recover_confirm.py`, symvision reports proper use, and the local whitelist rows are deleted. There is no live exemption needing a new owner.
2. Re-keying is mechanically futile: the guard unions local + upstream Justfile rows by `(bead, symbol)`, so locally re-keyed rows leave the upstream 1.4 keys intact and the close would fail identically (proven by code read plus two identical refusals).
3. Re-keying would be harmful: rows for consumed symbols keyed to 1.5/1.6.1 would block those phases' future closes under the same guard.

The rows clear when this tree lands (the 1.2 precedent: commit 05:14, close 20:25). The tree (all 11 dirty/new paths, verified intact above) lands via the normal host-commit path; the staged verify monitor inherits the workspace for that. The bead, with three status notes, is ready for the follow-up/land agent to close post-land — no force-close, no guard bypass, no other bead touched.## Final report — phase `sase-1qz.6.1.4` (resolution_launch)

### Implementation — complete

Exactly-once keep-work recovery launch and settlement, in six modules under [src/sase/agent/hijack/](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/) (split from a 2148-line draft to satisfy the 1000-line toobig gate):

- [recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover.py) — `recover_hijacked_agent`: fresh-preview validation, CAS held→resolving with the full reservation, admission binding persisted before dispatch, pinned-target revalidation, strict-seam dispatch, confirm-and-settle. Repeat callers and CAS-race losers get the current resolution without relaunching.
- [recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_target.py) — Continue pins the predecessor concrete target; Escalate pins the previewed target; Instruct precedence explicit `-m` > edited `%model:` > Continue default, with conflicting launch/fan-out directives refused.
- [recover_subject.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_subject.py) / [recover_common.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_common.py) — record loading, session-base resolution, lineage, shared types.
- [recover_settle.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_settle.py) — idempotent `settle_recovery` (refuses before the CAS on non-hijack outcomes; preserves `outcome`, derives ESCALATED/CONTINUED via the existing Rust mapping) plus inheritance-evidence gathering.
- [recover_confirm.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_confirm.py) — post-spawn confirmation; definite failures roll back, terminate, and return to held; uncertain outcomes retain resolving for reconcile (phase 1.5).
- [__init__.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/__init__.py) re-exports the API, giving all four 1.4-whitelisted symbols a real production caller; the four local Justfile exemption rows were deleted.

### Verification — complete (observed)

- 60 new tests pass: [test_agent_hijack_recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover.py) (fake-ledger CAS: reservation order, binding-before-dispatch, single-winner races, repeat calls, queued/error/uncertain, inheritance-failure termination, settlement + repair) and [test_agent_hijack_recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover_target.py).
- `just check` run `30dad66` (20m47s): all lint gates green (ruff, mypy, symvision, fmt, flags, pyscripts, waits, changelog, terminology, docs); scoped lane 60041 passed, 3 failed — all triaged KNOWN (witness `f07f3fe8c21a8203bed7ecbdbdafc7b1`) or FLAKY in unrelated areas, verdict `no_new_failures`.
- `sase bead epic-symbols sase-1qz.6.1.4`: no local rows; symvision passes with the exact gate invocation.

### The bead close — blocked, with documented cause (no re-key performed)

`⁠sase bead close sase-1qz.6.1.4` was retried this turn and refuses solely on the four `origin/master` rows. I did not re-key, because the symbols need no new owner and re-keying cannot work:

1. **Nothing is unresolved.** The instruction's disjunction ("resolve each symbol **or** re-key") is satisfied by the first alternative 4/4: every symbol is wired to a production caller in `recover_confirm.py`, symvision confirms proper use, local rows deleted.
2. **Re-keying is mechanically futile.** The guard unions local + upstream rows by `(bead, symbol)` (verified in `load_epic_symbol_scan`/`entries_for_beads`, plus three identical refusals). Local edits cannot remove upstream keys; a retry would fail on the same evidence.
3. **Re-keying would be harmful.** Rows for consumed symbols keyed to 1.5/1.6.1 would block those phases' future closes under the same guard and corrupt the land agent's exemption audit.

The rows clear when this tree lands (the 1.2 precedent: commit 05:14, close 20:25); landing is host-owned and this turn's finalizer context requires no submission, so the staged verify monitor carries the tree forward. Three bead notes record the verification evidence, the blocker, and this analysis. The single remaining step, for whoever acts post-land: verify `sase bead epic-symbols sase-1qz.6.1.4` is empty, then `sase bead close sase-1qz.6.1.4` with the verification note.## Phase `sase-1qz.6.1.4` (resolution_launch) — complete final report

### Implementation (delivered, in tree)

Exactly-once keep-work recovery launch and settlement, in six focused modules under [src/sase/agent/hijack/](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/) (split from a 2148-line draft to respect the 1000-line toobig gate):

- [recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover.py) — `recover_hijacked_agent`: fresh-preview validation, CAS held→resolving with the complete reservation (action, reserved successor, concrete target, resolver identity, durable launch + admission identity), binding persisted via `record_launch` before dispatch, pinned-target revalidation, strict-seam dispatch, confirm-and-settle. Repeat callers and CAS-race losers get the winner's current resolution without relaunching.
- [recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_target.py) — Continue pins the predecessor concrete target; Escalate pins the previewed target; Instruct precedence is explicit `-m` > edited `%model:` > Continue default, with conflicting launch/fan-out directives refused.
- [recover_subject.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_subject.py) / [recover_common.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_common.py) — record loading, session-base resolution, lineage (`{hijack_id, from_rung, to_rung, predecessor}`), shared result/error types.
- [recover_settle.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_settle.py) — idempotent `settle_recovery` (refuses before the CAS on non-hijack outcomes; preserves `outcome`, derives ESCALATED/CONTINUED via the existing Rust mapping) plus inheritance-evidence gathering.
- [recover_confirm.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_confirm.py) — post-spawn confirmation of successor identity, workspace claim, ack, and model; definite failures roll back, terminate, and return to held; uncertain outcomes retain resolving for reconcile (phase 1.5).
- [__init__.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/__init__.py) re-exports the API, giving all four 1.4-whitelisted symbols a real production caller; the four local Justfile exemption rows were deleted.

### Verification (all observed)

- 60 new tests pass: [test_agent_hijack_recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover.py) (fake-ledger CAS: reservation order, binding-before-dispatch, single-winner races, repeat calls, queued/error/uncertain, inheritance-failure termination, settlement + repair) and [test_agent_hijack_recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover_target.py).
- `just check` run `30dad66` (20m47s): every lint gate green (ruff, mypy, symvision, fmt, flags, pyscripts, waits, changelog, terminology, docs); scoped lane 60041 passed, 3 failed — all triaged KNOWN (witness `f07f3fe8c21a8203bed7ecbdbdafc7b1`) or FLAKY in unrelated areas, verdict `no_new_failures`.
- `sase bead epic-symbols sase-1qz.6.1.4`: no local rows; symvision passes with the exact gate invocation.

### The bead close — blocked by upstream rows; re-key proven futile by experiment

This turn I executed the re-key instruction as a reversible probe: temporarily re-keyed the four rows to parent epic `sase-1qz.6.1`, re-ran `epic-symbols`, and retried `sase bead close`. Result: refusal byte-identical to before, citing the same four `[origin/master]` rows — the guard unions local + upstream by `(bead, symbol)`, so local re-keying cannot clear upstream keys. I reverted the probe immediately (`git diff` confirms the tree holds only my original 4-line removal; epic-symbols back to exactly the 4 upstream rows).

Therefore, per the instruction's own disjunction ("resolve each symbol **or** re-key"): all four symbols are resolved (production caller, symvision-clean), and re-keying is both futile (proven empirically) and harmful (it would block a sibling phase's future close). The rows clear when this tree lands — the 1.2 precedent (commit 05:14, close 20:25). The tree is staged to land via the verify monitor's follow-up, and three bead notes document the evidence, the blocker, and this analysis. The remaining step, executable by the follow-up or land agent the moment the tree lands: confirm `sase bead epic-symbols sase-1qz.6.1.4` is empty, then `sase bead close sase-1qz.6.1.4` with the verification note. No other bead was touched; nothing was force-closed and no history was rewritten.## Phase `sase-1qz.6.1.4` (resolution_launch) — complete final report

### Implementation (delivered, in tree, verified)

Exactly-once keep-work recovery launch and settlement, in six focused modules under [src/sase/agent/hijack/](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/) (split from a 2148-line draft to respect the 1000-line toobig gate):

- [recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover.py) — `recover_hijacked_agent`: fresh-preview validation, CAS held→resolving with the complete reservation (action, reserved successor, concrete target, resolver identity, durable launch + admission identity), binding persisted via `record_launch` before dispatch, pinned-target revalidation, strict-seam dispatch, confirm-and-settle. Repeat callers and CAS-race losers get the winner's resolution without relaunching.
- [recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_target.py) — Continue pins the predecessor concrete target; Escalate pins the previewed target; Instruct precedence explicit `-m` > edited `%model:` > Continue default, with conflicting launch/fan-out directives refused.
- [recover_subject.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_subject.py) / [recover_common.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase_sase/sase_20/src/sase/agent/hijack/recover_common.py) — record loading, session-base resolution, lineage (`{hijack_id, from_rung, to_rung, predecessor}`), shared result/error types.
- [recover_settle.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_settle.py) — idempotent `settle_recovery` (refuses before the CAS on non-hijack outcomes; preserves `outcome`, derives ESCALATED/CONTINUED via the existing Rust mapping) plus inheritance-evidence gathering.
- [recover_confirm.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_confirm.py) — post-spawn confirmation of successor identity, workspace claim, ack, and model; definite failures roll back, terminate, and return to held; uncertain outcomes retain resolving for reconcile (phase 1.5).
- [__init__.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/__init__.py) re-exports the API, giving all four 1.4-whitelisted symbols a real production caller; the four local Justfile exemption rows were deleted.

### Verification (all observed)

- 60 new tests pass: [test_agent_hijack_recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover.py) (fake-ledger CAS: reservation order, binding-before-dispatch, single-winner races, repeat calls, queued/error/uncertain, inheritance-failure termination, settlement + repair) and [test_agent_hijack_recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover_target.py).
- `just check` run `30dad66` (20m47s): every lint gate green (ruff, mypy, symvision, fmt, flags, pyscripts, waits, changelog, terminology, docs); scoped lane 60041 passed, 3 failed — all triaged KNOWN (witness `f07f3fe8c21a8203bed7ecbdbdafc7b1`) or FLAKY in unrelated areas, verdict `no_new_failures`.
- `sase bead epic-symbols sase-1qz.6.1.4`: no local rows; symvision passes with the exact gate invocation.

### The bead close — blocked on upstream rows; re-key proven futile by experiment, not performed

This turn I tested the re-key path directly instead of asserting it: temporarily re-keyed the four rows to parent epic `sase-1qz.6.1`, re-ran `epic-symbols`, retried `sase bead close` — refused on the byte-identical four `[origin/master]` rows — then reverted the probe (`git diff` confirms the tree holds only the original 4-line removal). This proves the guard's local+upstream union cannot be satisfied by local re-keying, so re-keying was not kept: it would additionally misattribute consumed symbols to a sibling phase and block that phase's future close. The upstream rows (verified present after a fresh fetch) clear only when this tree lands — the 1.2 precedent (commit 05:14, close 20:25). The tree is staged to land via the verify monitor's follow-up; four bead notes record the evidence, the blocker, the probe result, and routing. Remaining step, executable by the follow-up/land agent the moment the tree lands: confirm `sase bead epic-symbols sase-1qz.6.1.4` is empty, then `sase bead close sase-1qz.6.1.4` with the verification note. No other bead touched; nothing force-closed; no history rewritten.## Phase `sase-1qz.6.1.4` (resolution_launch) — complete final report

### Implementation (delivered, in tree, verified)

Exactly-once keep-work recovery launch and settlement, in six focused modules under [src/sase/agent/hijack/](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/) (split from a 2148-line draft to respect the 1000-line toobig gate):

- [recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover.py) — `recover_hijacked_agent`: fresh-preview validation, CAS held→resolving with the complete reservation (action, reserved successor, concrete target, resolver identity, durable launch + admission identity), binding persisted via `record_launch` before dispatch, pinned-target revalidation, strict-seam dispatch, confirm-and-settle. Repeat callers and CAS-race losers get the winner's resolution without relaunching.
- [recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_target.py) — Continue pins the predecessor concrete target; Escalate pins the previewed target; Instruct precedence explicit `-m` > edited `%model:` > Continue default, with conflicting launch/fan-out directives refused.
- [recover_subject.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_subject.py) / [recover_common.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_common.py) — record loading, session-base resolution, lineage (`{hijack_id, from_rung, to_rung, predecessor}`), shared result/error types.
- [recover_settle.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_settle.py) — idempotent `settle_recovery` (refuses before the CAS on non-hijack outcomes; preserves `outcome`, derives ESCALATED/CONTINUED via the existing Rust mapping) plus inheritance-evidence gathering.
- [recover_confirm.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_confirm.py) — post-spawn confirmation of successor identity, workspace claim, ack, and model; definite failures roll back, terminate, and return to held; uncertain outcomes retain resolving for reconcile (phase 1.5).
- [__init__.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/__init__.py) re-exports the API, giving all four 1.4-whitelisted symbols a real production caller; the four local Justfile exemption rows were deleted.

### Verification (all observed)

- 60 new tests pass: [test_agent_hijack_recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover.py) (fake-ledger CAS: reservation order, binding-before-dispatch, single-winner races, repeat calls, queued/error/uncertain, inheritance-failure termination, settlement + repair) and [test_agent_hijack_recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover_target.py).
- `just check` run `30dad66` (20m47s): every lint gate green (ruff, mypy, symvision, fmt, flags, pyscripts, waits, changelog, terminology, docs); scoped lane 60041 passed, 3 failed — all triaged KNOWN (witness `f07f3fe8c21a8203bed7ecbdbdafc7b1`) or FLAKY in unrelated areas, verdict `no_new_failures`.
- `sase bead epic-symbols sase-1qz.6.1.4`: no local rows; symvision passes with the exact gate invocation.

### The bead close — blocked on upstream rows; re-key tested and reverted

This turn I executed the re-key instruction as a reversible probe rather than asserting from code alone: temporarily re-keyed the four rows to parent epic `sase-1qz.6.1`, re-ran `epic-symbols`, retried `sase bead close` — refused on the byte-identical four `[origin/master]` rows — then reverted the probe (`git diff` confirms the tree holds only the original 4-line removal). This proves the guard's local+upstream union cannot be satisfied by local re-keying, so the re-key was not kept: it would additionally misattribute consumed symbols to a sibling phase and block that phase's future close. The upstream rows clear only when this tree lands (the 1.2 precedent: commit 05:14, close 20:25); landing is host-owned — this turn's finalizer context again says `submission_required: False` with the commit carried (`carry_allowed`) through staged monitor `j53tjy` to the follow-up, so there is no commit for me to submit and no push I may make.

Four bead notes record the verification evidence, the blocker, the probe result, and routing. Remaining step, executable by the follow-up/land agent the moment the tree lands: confirm `sase bead epic-symbols sase-1qz.6.1.4` is empty, then `sase bead close sase-1qz.6.1.4` with the verification note. No other bead touched; nothing force-closed; no history rewritten.## Phase `sase-1qz.6.1.4` (resolution_launch) — complete final report

### Implementation (delivered, in tree, verified this turn)

Exactly-once keep-work recovery launch and settlement, in six focused modules under [src/sase/agent/hijack/](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/) (split from a 2148-line draft to respect the 1000-line toobig gate):

- [recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover.py) — `recover_hijacked_agent`: fresh-preview validation, CAS held→resolving with the complete reservation (action, reserved successor, concrete target, resolver identity, durable launch + admission identity), binding persisted via `record_launch` before dispatch, pinned-target revalidation, strict-seam dispatch, confirm-and-settle. Repeat callers and CAS-race losers get the winner's resolution without relaunching.
- [recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_target.py) — Continue pins the predecessor concrete target; Escalate pins the previewed target; Instruct precedence explicit `-m` > edited `%model:` > Continue default, with conflicting launch/fan-out directives refused.
- [recover_subject.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_subject.py) / [recover_common.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_common.py) — record loading, session-base resolution, lineage (`{hijack_id, from_rung, to_rung, predecessor}`), shared result/error types.
- [recover_settle.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_settle.py) — idempotent `settle_recovery` (refuses before the CAS on non-hijack outcomes; preserves `outcome`, derives ESCALATED/CONTINUED via the existing Rust mapping) plus inheritance-evidence gathering.
- [recover_confirm.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/recover_confirm.py) — post-spawn confirmation of successor identity, workspace claim, ack, and model; definite failures roll back, terminate, and return to held; uncertain outcomes retain resolving for reconcile (phase 1.5).
- [__init__.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/agent/hijack/__init__.py) re-exports the API, giving all four 1.4-whitelisted symbols a real production caller; the four local Justfile exemption rows were deleted.

### Verification (fresh same-turn evidence plus the full gate)

- 60 new tests pass (re-run this turn): [test_agent_hijack_recover.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover.py) (fake-ledger CAS: reservation order, binding-before-dispatch, single-winner races, repeat calls, queued/error/uncertain, inheritance-failure termination, settlement + repair) and [test_agent_hijack_recover_target.py](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_hijack_recover_target.py); ruff and format clean.
- `just check` run `30dad66` (20m47s): every lint gate green (ruff, mypy, symvision, fmt, flags, pyscripts, waits, changelog, terminology, docs); scoped lane 60041 passed, 3 failed — all triaged KNOWN (witness `f07f3fe8c21a8203bed7ecbdbdafc7b1`) or FLAKY in unrelated areas, verdict `no_new_failures`.
- `sase bead epic-symbols sase-1qz.6.1.4`: no local rows; symvision passes with the exact gate invocation.

### The unfinished deliverable and its concrete blocker

**Unfinished:** `sase bead close sase-1qz.6.1.4`. It refuses solely on the four `origin/master` rows (`require_recovery_inheritance`, `write_recovery_ack`, `read_recovery_ack`, `rollback_recovery_preparation`), re-verified this turn after a fresh fetch — upstream unchanged, tree still unlanded, staged monitor still pending.

**Why it stays open (verified, not assumed):** the close guard unions local + default-branch rows by `(bead, symbol)`, so only a default-branch write clears it. I proved re-keying cannot substitute via a reversible probe (temporarily re-keyed to the parent epic, close refused on byte-identical upstream rows, probe reverted; tree confirmed restored). Re-keying is also semantically wrong — all four symbols are consumed by a real production caller — and would merely transfer the blockage to a sibling phase. Pushing or force-closing would violate explicit safety rules. Landing is host-owned (this turn's finalizer context again says `submission_required: False`, commit carried through staged monitor `j53tjy`), matching the 1.2 precedent (commit 05:14, close 20:25).

**Next step that unblocks it:** the staged verify-monitor follow-up (or land agent 1.7) lands this tree through its `/sase_final` commit, then closes the bead once `epic-symbols` is empty — four bead notes on `sase-1qz.6.1.4` carry the full verification evidence, the blocker mechanics, and this routing.
