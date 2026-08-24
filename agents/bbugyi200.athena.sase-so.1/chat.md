# Chat History - ace-run (sase-so.1)

- **TIMESTAMP:** 2026-08-24 07:54:08 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-so.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-so.1, bead=sase-so.1)
%clan(sase-so, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-so.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-so.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-so.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-so.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design, and the beads/memory rules so I can complete `sase-so.1` without touching parent status.

Phase 1 is the typed identity wire in `sase-core` plus Python adapters. I'll open that repo through the repo skill and load the related glossary terms.

The design is clear: extend the Rust identity wire, then mirror it in Python. I'll inspect the current parse, classify, and dispatch paths next.

I'll read the Rust identity types, classification, and dispatch reconstruction next so the new wire matches existing directive rules.

I have the identity contract and dispatch path. Next I’ll extend the Rust wire, then mirror it in Python and add the keyed-marker batch resolution.

Rust agent-launch tests passed. Next I’ll run the full sase-core check, then rebuild the Python binding and run the sase tests.

`just check` passed after the scoped lane escalated. Next I’ll inspect epic-symbols, then close only `sase-so.1`.

Closed **sase-so.1** (`Preserve grouped identity through typed launch planning`). Parent epic `sase-so` is still open. No leftover `--epic-symbol` entries.

Typed launch now keeps the full identity binding instead of a positional name:

- **Rust `AgentUnitWire`** stores member id, clan join vs declaration, tribe, summary/summary script, family attach, and force-reuse. Schema-v1 JSON still deserializes as plain identity.
- **Classification** keeps `%id` keywords (`clan=`, `family=`, `tribe=`, `bead=`) and `%clan` arguments, with field-specific errors for malformed or conflicting forms.
- **`agent_unit_dispatch_prompt`** rebuilds `%id` and optional `%clan`, then the existing model/effort/auto/final/hide/wait-runner directives, still omitting `%if` and logical waits.
- **Python wire** mirrors those fields. **`plan_typed_launch_units`** resolves keyed `{@<id>}` markers once across the expanded batch before units are split; fenced and xprompt-disabled markers stay literal.
- Docs in `xprompt.md`, `architecture.md`, and `configuration.md` describe that identity directives survive admission and that keyed markers resolve at plan creation.

Verified: sase-core agent-launch tests plus the prescribed check (fmt, clippy, tests); SASE `just install`, focused typed-identity tests, and `just check` (scoped lane escalated to the full suite for `core-identity-changed` and passed).
