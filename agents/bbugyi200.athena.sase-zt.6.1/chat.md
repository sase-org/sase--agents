# Chat History - ace-run (sase-zt.6.1)

- **TIMESTAMP:** 2026-09-13 08:18:45 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-zt.6.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-zt.6.1, bead=sase-zt.6.1)
%clan(sase-zt.6, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-zt.6.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-zt.6.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-zt.6.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-zt.6.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the SASE skills that govern this phase.

The bead is in progress. Next I’ll read the epic plan, bead page, and the surrounding contracts so the work is grounded.

I’ll open sase-core, the original plan, and the audit artifact so the core-contracts work is based on the actual gaps.

I’ll open sase-core and pull the original plan, prompt, and audit so the contract work matches the landing gaps.

Configured lookup didn’t find sase-core, so I’ll open it as the sanctioned external repo and inspect the current wire and scanner.

sase-core is open. Next I’ll inspect the wire, scanner, launch, editor, and tests so the capacity contract is complete rather than patched.

I’ll read the wire types, scanner, launch paths, editor, and index next so dual-spelling capacity can land without dropping fields.

I have the contract seams. Next I’ll add shared capacity helpers, then wire them through scan, index, launch, editor, and tests.

I’ll add the shared capacity helpers first, then thread them through the scan, launch, and editor types.

I’ll format and compile the focused capacity tests next so any remaining type or import issues show up quickly.

I’ll keep ACE’s `directive_contract()` call unflagged so it still works against the current core pin; live completion already gets flags through inventories.

Closed **sase-zt.6.1**. Canonical `queue_capacity` now survives real Rust scans, waiting markers, launch wires, and indexed history, and the editor no longer suggests an invalid zero when the budget flag is on.

**Rust contract (sase-core)**
- `AgentMetaWire` and `WaitingMarkerWire` read `queue_capacity` / `queue_capacity_explicit`, with `wait_runners` as a legacy alias. Canonical wins on dual-written records; omission, explicit false, and explicit zero stay distinct. Writers emit canonical names.
- Scan wire **8→9**, artifact index **28→29**, so cached rows rebuild instead of storing missing capacity forever.
- Launch units expose `queue_capacity` (legacy `wait_runners` still accepted).
- `normalize_persisted_queue_capacity` is the shared drain translation: persisted explicit zero becomes the exact effective weight (for example 0.25 stays 0.25), and `reauthor_capacity` is omitted so continuations do not re-parse authored zero.
- `%queue` editor/LSP help is flag-aware: On suggests `1`/`100` as a positive budget; Off keeps the old `0` drain and threshold text.

**ACE**
- LSP gets `SASE_QUEUE_CAPACITY_BUDGET`.
- Directive contract calls pass enabled flags when the new binding is present, and fall back if the installed wheel is older.

**Verified** with `PYO3_PYTHON=/usr/bin/python3`: `cargo fmt --check`, `clippy -D warnings`, sase_core **2644** tests, sase_core_py **144** tests, and sase_xprompt_lsp tests. Parent core SHA: `a64c40d`.

**Not this phase:** `just check` also hit `sase_gateway` `fleet_mutate_refuses_terminal_missing_capability_and_bridge_failure` (`seeded fleet row`). That crate was not changed. Recorded as a proposed follow-up on the phase bead. Corroborated existing **sase-yn** for the provider-priority `LockTimeout` under parallel load.

sase-zt.6.2 should pin the core stitch this turn produces, then adopt the new scan/index schemas in Python.
