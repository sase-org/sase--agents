# Chat History - ace-run (sase-17m.2.1.1)

- **TIMESTAMP:** 2026-09-24 00:12:15 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17m.2.1.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-17m.2.1.1, bead=sase-17m.2.1.1)
%clan(sase-17m.2.1, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-17m.2.1.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17m.2.1.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17m.2.1.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17m.2.1.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17m.2.1.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-17m.2.1.1 (identity-directives) is complete.

What landed:

- sase-core: renamed `agent_family.rs` to `agent_session.rs` (wires, resolver, schema constant renamed with value unchanged), `parse_agent_family_name` to `parse_agent_session_name` plus the relationship/link, launch, hold, artifact-link, editor, and LSP concept renames. All serialized output stays byte-identical via `rename=legacy, alias=new` pins; inputs accept both spellings (`%id` takes `session=` and `family=`, both together is `invalid-id-session`). Completion, snippets, and hover now offer only `session=` while `family=` stays accepted and in the contract. Added `parse_agent_session_name` / `resolve_agent_session_parent` pyo3 bindings next to the legacy names. Reserved `session`/`sessions` for new names (no existing agent uses them).
- sase companion: `_looks_like_id_keyword_prefix` accepts `session`, and the directive-contract plus ACE completion tests accept both core shapes.

Verification observed: `sase tool run check` passes in sase-core; all targeted core/LSP/binding tests pass; sase companion tests pass (contract, completion candidates, ACE/LSP parity, family-attach, hold, diagnostics). `sase bead epic-symbols` shows no leftover entries. One pre-existing, unrelated failure: sase `just check` is red on mypy in `file_panel/_content.py` (proven present with my changes stashed); recorded on the bead as a follow-up note, along with the wire-cutover tightening note and the remaining-`famil` classification.

Final declaration accepted for commit (sase repo closes the bead, sase-core keeps); uncommitted work is now the host finalizer's.
