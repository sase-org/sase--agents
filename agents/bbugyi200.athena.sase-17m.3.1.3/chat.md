# Chat History - ace-run (sase-17m.3.1.3)

- **TIMESTAMP:** 2026-09-24 06:38:36 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17m.3.1.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-17m.3.1, bead=sase-17m.3.1.3)
%model:@medium
%auto
%w:sase-17m.3.1.2
%w(bead=sase-17m.3.1.2)
Can you complete the work for bead sase-17m.3.1.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17m.3.1.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17m.3.1.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17m.3.1.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17m.3.1.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-17m.3.1.3 is done and closed.

**What changed** — Python wire mirrors hydrate either spelling and emit new spellings:
- `agent_scan_wire_family_shell.py` → `agent_scan_wire_agent_session_shell.py` (`AgentSessionShell*Wire`, `agent_session_shell_from_mapping`); `AgentMetaWire`/`DoneMarkerWire` fields renamed with either-spelling hydrators; `with_legacy_agent_session_keys` replaced by forward `with_agent_session_keys`.
- Cleanup, group-archive (`canonical_global_agent_session`), runner-slot records/predicates, hold payloads (`session`), wait-dep shell helpers, `agent_session_settled`/`AgentSessionIndexCache` renamed.
- Fleet identity/nodes/rows/promotion read new keys first (`agent_session_id` locator verified against core); `promote_family_follow` → `promote_agent_session_follow`; all importers updated.
- One boundary exception per plan policy: core's capacity struct has no `agent_session_parallel` alias (probed live), so `capacity_session_keys_for_core` still sends that one legacy key.

**Verified** — 12 new tests in [tests/test_agent_session_wire_mirrors.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_agent_session_wire_mirrors.py), including real `sase_core_rs` round trips; ~4000 focused tests green; ruff/mypy/fmt and all other `just check` gates green. `sase bead epic-symbols` clean; shell test file renamed to match the module; 4 follow-ups recorded on the bead.

**Findings** — `just check` can't fully pass: the symvision private-import gate fails identically on pristine base HEAD (73 violations, 41 untouched files), so it's pre-existing and out of scope. Also, `sase final prepare` is blocked by pre-existing foreign dirt (Aug 29) in the shared agents sidecar plus a no-deferrals policy on conditional completion; I closed via `sase bead close` and committed via plain `sase final submit`, both accepted.

Left deliberately for sibling phases: ACE `Agent(` kwargs/fields (3.1.4), family-attach machinery and CLI output keys (runtime-cutover), wait-index domain vocabulary and source-kind values (durable-json), relation-kind values (ace-cutover).
