# Chat History - ace-run (sase-on.2)

- **TIMESTAMP:** 2026-08-17 12:38:20 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-on.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-on, bead=sase-on.2)
%model:@medium
%auto
Can you complete the work for bead sase-on.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-on.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-on.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-on.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the relevant SASE memory so I can complete `sase-on.2` without touching the parent epic.

Next I’ll load bead memory and inspect `sase-on.2` so I know the phase scope before touching code.

The phase is the BeadStaleCleanup gate contract. I’ll read the plan, parent epic, and existing gate patterns next.

The plan is large; I’ll pull the gate-phase section and look at existing gate implementations to match.

I have the gate-phase contract. Next I’ll map the flag-triage layout and existing bead-gate modules so the new kind matches them.

I’ll keep going through the flag-triage validation, adapters, and task-gate helpers so the new contract can follow the same pattern.

Adding a registered kind will touch a few exhaustive maps. I’ll find those next, including the mobile action-kind table.

I have the flag-triage pattern and the registration points. Next I’ll implement the gate contract and the tests the plan lists.

Install is still running; I’ll write the gate modules and wire registration while it finishes.

Next I’ll register the new kind in the adapter, validator, priority list, and debug icons.

I’ll add the test helpers and the spec, preview, validation, and command tests next.

Install finished. I’ll run the new gate tests first, then fix anything they surface.

Command scripts are failing on import, and one validation case is raising the wrong error. I’ll inspect both next.

The command-script crash is a circular import: the spec pulls in `task_gate`, which loads kind validation, which imports the spec again. I’ll break that cycle.

The payload parser’s module-level import of the spec is what closes the cycle. I’ll move that import into the parse function.

The new tests passed. Next I’ll run `just check` for the whole-repo lint gates and the diff-scoped test lane.

The feature-flag lint failure looks unrelated. I’ll confirm that before treating it as follow-up rather than a regression from this phase.

The flag-lint miss is on live bead `sase-om`, which this phase did not touch. I’ll record that as follow-up and run the remaining `just check` stages against my changes.

Symvision says two whitelist entries are wrong: I’ll drop those and keep only `create_bead_stale_cleanup_gate`.

`BeadStaleCleanupBead` is only used inside its module, so I’ll make it private to satisfy Symvision.

Symvision is clean. I’ll run the remaining check stages, including the scoped tests.

The scoped run escalated to the full suite and passed. I’ll check leftover epic-symbols for this phase, then close the bead.

`sase-on.2` is closed. The trusted **BeadStaleCleanup** gate contract is in place; the parent epic `sase-on` is still open.

## What landed

A new `bead_stale_cleanup` gate kind, modeled on FlagTriage:

| Piece | Where |
| --- | --- |
| Facade | `src/sase/bead/stale_cleanup_gate.py` |
| Constants, spec, command | `src/sase/bead/_stale_cleanup_gate_spec.py` |
| Payload-pure preview | `src/sase/bead/_stale_cleanup_gate_preview.py` |
| Response translation | `src/sase/bead/_stale_cleanup_gate_response.py` |
| Payload parse | `src/sase/notification_gates/kind_validation/bead_stale_cleanup_payload.py` |
| Kind validation | `src/sase/notification_gates/kind_validation/bead_stale_cleanup.py` |

The adapter is registered as **Stale Task Cleanup** / `BeadStaleCleanup`: human-only (`auto` forbidden), `generic_form`, optional feedback, `🧹`. `apply_side_effects` is intentionally unwired — that is `sase-on.3`.

Reviewer contract:

- One **Close selected** option
- One non-required `bead_N` enum per roster row (`close` / `keep`, default `close`)
- Missing fields mean close
- All-keep exits `2` with `select at least one bead to close, or dismiss this gate` so the gate stays pending
- Preview and ages are functions of the payload (`stale_as_of`), not the wall clock
- Project labels go through `project_display_name_for` — no ProjectSpec keys in user-facing text
- Translation maps `close_bead_indexes` back through the persisted roster; a forged index cannot name a bead the gate never offered

`create_bead_stale_cleanup_gate(...)` is the chop’s entry point. It is still unused outside tests, so it is whitelisted as `--epic-symbol "sase-on(create_bead_stale_cleanup_gate)"` until `sase-on.4` consumes it. `sase bead epic-symbols sase-on.2` is empty.

Host close effects stay out of this phase (`sase-on.3`).

## Verification

- Dedicated tests: spec/command, preview, validation, translation
- `test-scoped` escalated to the full suite (Justfile change) and passed
- Lint of this tree (fmt, ruff, mypy, symvision, toobig) is green

Two `just check` stages failed for reasons this phase did not cause; both are on the bead as `PROPOSED FOLLOW-UP:`:

1. Feature-flag rule 8: live flag bead `sase-om` (`completion_refresh_on_update`) has no registry definition in this tree
2. `sase validate` / `init memory --check` wants a chezmoi refresh of home `AGENTS.md` and provider shims

I'll verify the bead close, then commit the `sase-on.2` changes using the required workflow. First I need the commit skill, bead status, and current git state.

The bead is closed locally; I'll republish the close, then review the diff and commit.

The close command is still publishing; I’ll wait for it before writing the commit.

The close published successfully. Next I’ll write the commit message and create the stitch.

The stitch landed. I'll confirm the branch is clean and not ahead of upstream.

Published the `sase-on.2` close and committed the BeadStaleCleanup gate contract.

**Bead:** `sase-on.2` was already closed; `sase bead close` republished it (exit 0) and recorded the verification note. `sase bead epic-symbols sase-on.2` is empty. Parent epic `sase-on` is still open.

**Commit:** `3cfc5ddf4` — `feat(gates): add BeadStaleCleanup notification gate contract`  
`master` matches `origin/master`; working tree is clean.

The stitch reported 12 quarantined agent-hood publication requests (last error: `sase-oo` timed out at 120s). The commit itself is on the remote. Clear the outbox later with `sase agent sync --retry-quarantined` if those hoods still need publishing.
