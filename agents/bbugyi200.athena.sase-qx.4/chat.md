# Chat History - ace-run (sase-qx.4)

- **TIMESTAMP:** 2026-08-19 14:48:52 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-qx.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-qx, bead=sase-qx.4)
%model:@medium
%auto
%w:sase-qx.2
%w(bead=sase-qx.2)
Can you complete the work for bead sase-qx.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-qx.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-qx.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-qx.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the relevant SASE skills so the work matches the phase instructions.

The phase is a launch guard for hard-disabled providers. Next I’ll read the plan, the bead page, and prior phase work.

Routing is already in; next I’ll inspect the launch path, existing helpers, and conventions so the guard can land in the right place.

I have the launch path and routing pieces. Next I’ll add the guard module and wire it into `sase run` and the CWD launcher.

I’ll clean up the error-message helper, then wire the guard into the launch path.

The module-level `launch_guard` import is closing a cycle through `agent` → `llm_provider`. I’ll make that import lazy.

The scoped suite failed on launch-query mocks that don’t accept the new kwargs. I’ll update those tests next.

**sase-qx.4 is closed.** The fail-closed launch guard is in place: a launch that can only run on a hard-disabled provider is refused before anything spawns.

### What landed

- New `src/sase/agent/launch_guard.py` enumerates launch **units** (one expanded segment each). `%repeat` / `%alt` / `%{%m:…}` fan-out become **candidates** of that unit, so a blocked branch cannot hide.
- Fast path: if `peek_active_provider_disables()` has no **hard** disable, nothing is planned.
- A unit is blocked only when every candidate is hard-disabled or unavailable **and** at least one is hard-disabled. Soft disables never refuse. Pool cursors are not consumed (`consume=False`).
- `launch_agents_from_cwd_impl` runs the guard after expansion and before name resolution, workspace claim, or spawn. A confirmed block raises `DisabledProviderLaunchError` (names the provider, window, why there is no fallback, and `Enable it in ACE Launch Control (,m → p) or choose another model.`), and stashes the failed prompt. Any other guard exception is logged and the launch continues.
- `sase run` accepts a strict `launch_units` payload (`prompt`, `template_group`, `swarm_xprompts`) and ignores it when force-reuse applies.

### Verification

- 31 new tests in `tests/agent/test_launch_guard.py` and `tests/agent/test_launch_cwd_guard.py`.
- `just check`: lint/mypy/symvision/toobig/SASE validation green. No `--epic-symbol` leftovers on **sase-qx.4**; `LaunchUnit`, `LaunchUnitCandidate`, `plan_launch_units`, and `blocked_launch_units` are keyed to **sase-qx.5** for the ACE panel.
- Full-suite escalation (Justfile) had 3 failures, all unrelated: two completion-spec snapshot drifts already on master, and one leak-detector flake that passes in isolation. Those are on the bead as `PROPOSED FOLLOW-UP` notes.

Parent epic **sase-qx** was not closed. The ACE panel phase (**sase-qx.5**) is unblocked on this work.

I'll start by reading the commit skill and checking bead/git state so the close and commit can finish in this turn.

The bead is already closed. I’ll re-run close to publish it, then inspect the diff and commit.

The close command is still running; I’ll wait for it to finish before committing.

Close published (already closed; note recorded). Next I’ll record the commit skill and create the commit.

Rebase conflicted on `Justfile`. I’ll resolve it, continue the rebase, then resume the stitch.

I’ll keep both sides of the Justfile conflict: our `sase-qx.5` symbols and the upstream `sase-r1` ones.

Rebase finished cleanly. Next I’ll resume the stitch so the commit is pushed.

**sase-qx.4 is closed and committed.**

Re-ran `sase bead close sase-qx.4` (already closed; verification note published). Committed the fail-closed launch guard as `feat(agent): refuse launches that can only run on a hard-disabled provider` (`44415dddd`).

A rebase conflict in `Justfile` was resolved by keeping both the `sase-qx.5` epic-symbol entries and the upstream `sase-r1.*` entries. Stitch resume pushed the commit; `master` matches `origin/master` and the working tree is clean.

Parent epic **sase-qx** was not closed.
