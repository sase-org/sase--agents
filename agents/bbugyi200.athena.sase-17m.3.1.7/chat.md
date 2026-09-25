# Chat History - ace-run (sase-17m.3.1.7)

- **TIMESTAMP:** 2026-09-24 10:50:11 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17m.3.1.7

## Prompt

#gh:gh_sase-org__sase
%id(7, clan=sase-17m.3.1, bead=sase-17m.3.1.7)
%model:@small
%auto
%w:sase-17m.3.1.5,sase-17m.3.1.6
%w(bead=sase-17m.3.1.5)
%w(bead=sase-17m.3.1.6)
Can you complete the work for bead sase-17m.3.1.7? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17m.3.1.7 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17m.3.1.7 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17m.3.1.7`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17m.3.1.7 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-17m.3.1.7 is complete and closed.

What was done:

- **Classification sweep**: every remaining `agent_family` / `family_shell` literal in `src` was reviewed. All are inside named legacy readers or boundary helpers carrying `# legacy agent-family spelling` comments (plan_chain `LEGACY_*` constants, `agent_bundle.py` migration table, fleet new-then-legacy hydrations, capacity `agent_family_parallel` boundary awaiting core-contract). The one un-commented emitter, `cli_list.py` lines 100-101, is CLI JSON output explicitly owned by runtime-cutover per the plan scope boundary.
- **Test coverage confirmed**: legacy-input plus no-legacy-emitted tests exist for all durable surfaces, wire mirrors, canonical keys, the Agent model, and the name-registry v2→v3 upgrade. Ran the five focused files: 113 passed.
- **`sase tool run check`**: fails only in `_setup` on `tool_run_claim` / `tool_run_request_stop` bindings required by HEAD's validator but absent from the pinned core (eef7ca4). Verified the built extension has the new agent-session bindings and lacks only those two unrelated tool bindings, so this is out-of-scope breakage — recorded as a `PROPOSED FOLLOW-UP` on the bead rather than fixed.
- **Hand-offs**: recorded runtime-cutover, ace-cutover, and core-contract notes on the sase-17m.3 phase bead. No `--epic-symbol` entries remained, and no code was changed (verify-only turn, tree clean).
