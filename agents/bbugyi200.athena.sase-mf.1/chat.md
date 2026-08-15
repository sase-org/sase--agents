# Chat History - ace-run (sase-mf.1)

- **TIMESTAMP:** 2026-08-15 14:57:17 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-mf.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-mf.1, bead=sase-mf.1)
%clan(sase-mf, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium_worker
%auto
Can you complete the work for bead sase-mf.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-mf.1 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-mf.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the bead/memory skills so the work matches the reserved `sase-mf.1` assignment.

Next I’ll load bead memory and inspect `sase-mf.1` so the implementation matches the assigned phase.

The phase is in Rust core: I’ll read the plan, backend-boundary notes, and the repo skill before changing anything.

Phase 1 is the shared Rust routing contract. I’ll inspect how `sase-core` already models sizes and bindings so the new module matches it.

I’ll compare existing small domain modules and the current Python size-to-alias mapping so the new contract stays consistent.

I’ll inspect binding style, existing size routing in core, and any Python parity probes this phase should extend.

I’ll add the size parser and the new routing module first, then wire it through the crate exports.

Bindings next: I’ll expose the new routing functions on the Python module and add tests that call them through PyO3.

I’ll switch the binding tests to `json_value_to_py` so integer/bool construction stays on the PyO3 0.22 APIs this crate already uses.

Unit tests passed. Next I’ll compile the PyO3 binding tests, then run the full sase-core gate.

Bindings look good. I’ll run the full sase-core `just check` next — that’s the phase handoff gate.

`just check` passed. I’ll close `sase-mf.1` with the verification note.

`sase-mf.1` is closed. The parent epic `sase-mf` is still open.

The shared routing contract now lives in the linked `sase-core` checkout as a provider-agnostic domain module plus PyO3 bindings. Phase 2 (`alias_config_contract`) can call these instead of maintaining Python size maps.

### Contract

`size_model_route(size)` maps every `PhaseSizeWire` to the public `@<size>` alias:

| Size | Alias |
| --- | --- |
| `xsmall` | `@xsmall` |
| `small` | `@small` |
| `medium` | `@medium` |
| `large` | `@large` |
| `xlarge` | `@xlarge` |

Bare names and `@`-prefixed names both work. Retired names such as `medium_worker` and `epic_lander` are rejected, not rewritten.

`select_epic_land_model(explicit_model, phase_count, threshold, epic_lander_model, big_epic_lander_model)`:

1. A non-empty explicit model wins.
2. Otherwise `phase_count >= threshold` selects the configured big target.
3. Otherwise it selects the configured normal target.

Provenance uses config-field names (`explicit`, `epic_lander_model`, `big_epic_lander_model`), not fake aliases. Invalid sizes, negative counts, non-positive thresholds, booleans, empty targets, and control characters fail at the binding.

### Where it is

Uncommitted in the linked `sase-core` tree:

- `crates/sase_core/src/model_route.rs`
- `PhaseSizeWire::from_name` / `NAMES` in `bead/wire.rs`
- Python: `sase_core_rs.size_model_route` and `sase_core_rs.select_epic_land_model`

Historical `agent_scan` fixtures that store `large_worker` / `medium_worker` metadata were left as-is.

### Verified

Linked `sase-core` `just check` passed: rustfmt, clippy with warnings denied, and `cargo test --workspace` (including the new unit and binding tests).

I'll close the reserved bead first, then commit the linked `sase-core` changes with the git-commit skill.

I'll close the bead, inspect the linked `sase-core` diff, and record the commit-skill invocation.

The first `git status` ran in the Python workspace, not `sase-core`. I'll inspect the linked repo and wait for the bead close.

The bead is already closed. Next I’ll review the `sase-core` diff so the commit message matches the routing-contract change.

Those commands ran in the Python workspace. I’ll re-inspect the linked `sase-core` tree explicitly.

I'll write the conventional commit message and create the stitch from the linked `sase-core` checkout.

The message landed in the Python workspace. I’ll write it in the linked `sase-core` tree and commit from there.

The commit succeeded. I’ll confirm the linked `sase-core` tree is clean and in sync with upstream.

`sase-mf.1` is closed, and the linked `sase-core` work is committed and pushed.

**Bead.** `sase bead close sase-mf.1` reported the phase already closed (`done` at 2026-08-15T18:49:54Z) and appended the verification note: linked `sase-core` `just check` passed (rustfmt, clippy `-D warnings`, `cargo test --workspace`, including the new unit and PyO3 binding tests). Parent epic `sase-mf` is still open.

**Commit.** In `sase-core` (`master` / `origin/master`, clean, 0 ahead/0 behind):

`b360211` — `feat(model_route): add shared size and epic-land routing primitives`

That stitch adds `model_route.rs`, `PhaseSizeWire::from_name` / `NAMES`, and the PyO3 bindings `size_model_route` / `select_epic_land_model`.

Stitch create warned that this project already has 3 quarantined agent-hood publication requests; the commit itself landed. `sase agent sync --retry-quarantined` would retry those separately.
