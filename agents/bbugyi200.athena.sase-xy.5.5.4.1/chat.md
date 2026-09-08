# Chat History - ace-run (sase-xy.5.5.4.1)

- **TIMESTAMP:** 2026-09-07 23:51:09 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-xy.5.5.4.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-xy.5.5.4.1, bead=sase-xy.5.5.4.1)
%clan(sase-xy.5.5.4, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-xy.5.5.4.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-xy.5.5.4.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-xy.5.5.4.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-xy.5.5.4.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, the beads/memory rules, and the design file so the work matches what this phase actually requires.

Phase 1 is in `sase-core`: source-directory resolution must prove owner provenance. I'll open that repo and inspect the current resolver.

I’ll inspect the wire types, PyO3 bindings, and how Python currently uses `project_key` so provenance checks can sit on real identity, not a decorative field.

I’ll bound source-directory hits to proved owner checkouts and make `project_key` actually constrain inventory, then add the regression tests from the plan.

I'll format the Rust changes and run the sase-core check surface next.

Closed **sase-xy.5.5.4.1**. Source-directory resolution now requires proved owner provenance; an unrelated path is no longer relabeled as the owner repository.

A source-relative hit is eligible only when the source directory sits inside a live attached checkout or a live inventory checkout. Setting `owner.repository` no longer stamps that name onto a directory outside every checkout for that repository. `owner.project_key` now constrains inventory: those checkouts are used only when `context.selected_project` agrees (name, key, alias, or `gh_` slug). Attached producer workspaces still resolve without that agreement, and a stale source directory still falls through to a live same-repository checkout when inventory is in scope.

Python now sends `selected_project` on the context wire and passes the owner project into context assembly, so the field is not decorative.

Verified:
- Out-of-inventory `secret.py` is `proven_missing`, not `exact` as `owner`
- Owner-repository mismatch, owner-project mismatch, unavailable project context
- Nested source directory with project agreement
- Correlated producer workspace without inventory
- Stale-source fallback to a live same-repo checkout
- Existing directory, filter, revision, ambiguity, traversal, and suffix-budget cases
- `sase-core` `just check` green, including the PyO3 rejection
- `sase` `just check` green
- No leftover `--epic-symbol` entries for this phase

The parent epic was left open.
