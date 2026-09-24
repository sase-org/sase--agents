# Chat History - ace-run (sase-17m.3.1.2)

- **TIMESTAMP:** 2026-09-24 05:25:43 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17m.3.1.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-17m.3.1, bead=sase-17m.3.1.2)
%model:@medium
%auto
%w:sase-17m.3.1.1
%w(bead=sase-17m.3.1.1)
Can you complete the work for bead sase-17m.3.1.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17m.3.1.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17m.3.1.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17m.3.1.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17m.3.1.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-17m.3.1.2 (canonical-keys) is done and closed.

What landed:

- `src/sase/plan_chain.py` now owns `AGENT_SESSION_KEY/ROLE/PARALLEL/SHELL_KEY`, `AGENT_SESSION_SEPARATOR`, and `LEGACY_AGENT_FAMILY_*` constants (the only place naming legacy keys), plus new-then-legacy accessors (`agent_session_value` etc. for mappings and objects), `set_agent_session_fields` / `strip_legacy_agent_family_keys` writer helpers, and renamed `agent_session_*` helpers with deprecated `agent_family_*` aliases so ~250 call sites keep working.
- Routed ~35 reader files (agent_meta/done.json lookups, name resolution, gate/monitor lanes, ACE loaders, wait/restart paths) through the accessors; writers (promotion, directive metadata, followup artifacts, inventory canonicalization, reclaim, wait classify) emit only new keys and drop legacy on rewrite. `family_shell_from_mapping` reads the new nested key first; v2 validation accepts both spellings.
- Added a temporary, marked bridge (`with_legacy_agent_session_keys` in `core/wire.py`) so new-keyed files still hydrate the legacy-named `AgentMetaWire`/`DoneMarkerWire` fields until wire-mirrors renames them — recorded as a `PROPOSED FOLLOW-UP` for sase-17m.3.1.3 to remove. Later phases own: Agent field renames, wire/fleet/hold/runner-slot mirrors, `family:` kind values, attach internals, and CLI output keys.
- Tests: new `tests/test_plan_chain_agent_session_keys.py` (17 tests: legacy/mixed/new reads, no-legacy writes, bridge); updated writer-output assertions across 10 test files to assert new keys and legacy absence. `sase bead epic-symbols` is clean.

Verification: `just fmt`, ruff, mypy (4892 files clean), keep-sorted and other lint gates pass; ~1000 targeted tests green. Two pre-existing failures proven identical on clean HEAD and left alone: symvision (73 repo-wide errors) and one completion bead-candidates test. I also fixed one pre-existing mypy error in `file_panel/_content.py` that was blocking the gate.
