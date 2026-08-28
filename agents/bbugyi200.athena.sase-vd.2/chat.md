# Chat History - ace-run (sase-vd.2)

- **TIMESTAMP:** 2026-08-28 18:46:00 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-vd.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-vd, bead=sase-vd.2)
%model:@medium
%auto
Can you complete the work for bead sase-vd.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-vd.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-vd.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-vd.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead description, design file, and the beads/memory rules so I can complete `sase-vd.2` without touching ancestor status.

The phase is about threading the starter’s VCS workflow ref through shell follow-up launches. Next I’ll read the epic plan and the current launch path.

Phase 2 is the VCS-ref threading path. I’ll open the GitHub plugin repo and inspect the current spawn/follow-up code.

I’ve got the spawn path; next I’ll inspect how shell member meta is written and how retry already threads `vcs_ref`.

I have the spawn and member-meta shape. Next I’ll thread the starter VCS ref through shell creation and follow-up launches, then add tests.

I’ll add tests for recorded VCS refs, prompt recovery, `#0` fallback, and non-VCS follow-ups.

I’ll simplify the workflow-metadata fixture so tests don’t depend on a private helper, then run the new tests.

The venv is missing the Rust extension, so I’ll install it and drop alias canonicalization from prompt recovery so that path stays registry-only.

Symvision flagged two follow-up helpers as unused public APIs. I’ll read the lint rules and make those names private.

Closed **sase-vd.2** (`preallocate-shell-followups`). Gate, monitor, and proc-shell follow-ups that still carry `#gh:`/`#git:` now spawn with the launcher’s pre-allocation env instead of allocating a second workspace.

What landed:

- The starter’s VCS workflow ref (`["gh", "sase"]`) is written to `agent_meta` at launch and inherited onto shell members.
- `launch_shell_followup` resolves that ref against the composed prompt and passes it through `spawn_family_successor` → `spawn_detached_child` → `spawn_agent_subprocess`.
- Gate and monitor spawn closures forward it. Older shells with no recorded ref recover it from the prompt via `get_embedded_vcs_tag_pattern()`.
- Pre-allocation env uses the workspace the follow-up actually got, including degraded `#0` fallbacks.

Verified:

- A `#gh:`-carrying gate-shell follow-up is spawned with `SASE_GH_PRE_ALLOCATED=1` and matching `_WORKSPACE_NUM`/`_WORKSPACE_DIR`.
- A degraded `#0` fallback advertises workspace 0.
- A non-VCS follow-up sets none of those three variables.
- `just check` passed. No leftover `--epic-symbol` entries for this phase. Parent epic **sase-vd** is still open.
