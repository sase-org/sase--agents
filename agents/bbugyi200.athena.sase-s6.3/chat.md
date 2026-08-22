# Chat History - ace-run (sase-s6.3)

- **TIMESTAMP:** 2026-08-22 21:49:29 UTC
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-s6.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-s6, bead=sase-s6.3)
%model:@medium
%auto
%w:sase-s6.2
%w(bead=sase-s6.2)
Can you complete the work for bead sase-s6.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-s6.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-s6.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-s6.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design, and the relevant SASE skills so the phase work stays on the assigned scope.

The bead is an in-progress phase for durable launch admission. Next I’ll read the plan, related memory, and the phase page so the implementation stays on that design.

Phase 3 is the durable admission coordinator. I’ll read the rest of the plan, prior phase work, and the research artifacts next.

I’ll explore the existing launch-approval and coordinator code in both repos while the research sidecar finishes opening.

I'll add the Rust admission state machine first, then wire the Python coordinator to it.

Rust admission tests passed. Next I’ll add the Python wires, coordinator, and launch-request integration.

I'll make the in-file-only APIs private and drive tests through the public dispatch entry so Symvision sees real consumers.

Closed **sase-s6.3** (Durable launch admission coordinator). The parent epic **sase-s6** is still open.

What landed:

- **Typed approval payload.** With `typed_launch_units` on, LaunchApproval stores the plan digest, schema, typed preview, and per-unit result summary. Flag-off and old all-agent requests still dispatch through the existing `launch_agents_from_cwd` path.
- **Durable coordinator.** After approval it journals per-unit phases (`reserved` → `waiting` → `checking`/`eligible` → `dispatching` → terminal), writes a request sidecar, and acknowledges startup. It is infrastructure on the launch-request bundle, not a proc shell or Agents-tab row. Remaining waits continue in a detached process.
- **Wait-before-resources.** Logical, agent, proc, bead, and time waits settle before conditions or dispatch. Waiting does not take runners, workspaces, proc records, or provider capacity. A skipped predecessor stays a terminal wait target (no retargeting).
- **Agent path preserved.** Eligible agent units still launch through the established agent launcher. Conditions and stand-alone procs have hooks for sase-s6.4 / sase-s6.5; until those land they settle as `condition_error` / `launch_error` without allocating resources.
- **Recovery.** Replay skips settled units, interrupted checks/dispatches do not re-run or double-spawn, and coordinator stop escalates SIGTERM then SIGKILL.

Verification: Rust admission tests, focused Python admission/approval tests, and `just check` (it escalated to the full suite because Justfile and core identity changed) all passed. `sase bead epic-symbols sase-s6.3` reported no leftovers for this phase.

`LaunchConditionWire` remains whitelisted on **sase-s6.4**; `LaunchPlanDiagnosticWire` stays on the parent epic until a later phase consumes it.
