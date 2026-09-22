# Chat History - ace-run (sase-16n.1)

- **TIMESTAMP:** 2026-09-22 19:49:04 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16n.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-16n.1, bead=sase-16n.1)
%clan(sase-16n, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-16n.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16n.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16n.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16n.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16n.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16n.1 (core-tags) is complete and closed.

What landed in sase-core:

- New `sase_core::project_tag` module — `scan_project_tags` (D1 grammar, literal-zone skipping via the shared scanners plus frontmatter, anchored detection), `resolve_project_tag` (exact, then casefold, ambiguous/unknown with top-3 suggestions), `expand_project_tags` (in-place rewrite to `#<workflow_type>:<key>` plus per-tag report, never errors), `project_tag_trigger` (D1 left boundary: start, whitespace, `{`, `|`), and `apply_project_tag_selection` (D7 in-place accept with same-segment other-target removal). 19 table-driven tests cover every D1 example, literal zones, multi-byte text, anchoring, resolution, expansion, and ported plus new accept vectors.
- Catalog wire v5 in `editor/wire.rs`: `VcsProjectEntry` gains serde-default `key`, `tag`, `accent_index`, `current`; new `VcsProjectCatalogWire` with `accent_palette` and `project_tags` plus `VCS_PROJECT_CATALOG_SCHEMA_VERSION = 5`. Wire tests prove v1 loads with defaults and v5 round-trips. The LSP loader accepts schemas 1–5 (new v5 loader tests).
- `vcs_project_trigger_token` is now a thin wrapper over the new trigger; `build_vcs_project_completion_candidates` runs on the shared accept algorithm (project rows insert `+name `, grammar-excluded names fall back to `#wf:name `, PR rows keep `#` spelling). Old prepend/replace helpers removed; completion and LSP tests updated to in-place expectations.
- Five `project_tag_*` bindings in a new `sase_core_py` domain, returning Python code-point offsets, with round-trip tests including multibyte offsets.

Verification: `sase tool run check` green, `sase bead epic-symbols` clean, bead closed, final commit declaration submitted.

Two things for downstream agents: suggestions use a small local Levenshtein ranker (names before keys before aliases on ties) because core has no edit-distance helper — `fuzzy_match` can't rank the D3 `+ssae`→`+sase` transposition. And LSP `detail` on project items temporarily mirrors the insertion (e.g. `+sase ` with trailing space) until the lsp phase restyles items to `GitHub · #gh:sase`.

Declaration accepted for the sase-core commit; bead sase-16n.1 work preserved (kept, already closed).
