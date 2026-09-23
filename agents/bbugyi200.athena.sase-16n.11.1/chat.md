# Chat History - ace-run (sase-16n.11.1)

- **TIMESTAMP:** 2026-09-23 09:24:49 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16n.11.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-16n.11.1, bead=sase-16n.11.1)
%clan(sase-16n.11, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-16n.11.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16n.11.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16n.11.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16n.11.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16n.11.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16n.11.1 (core-fixes) is done and closed. All work is in the linked sase-core checkout, 20 files changed.

What was implemented, per the phase plan:

- **Accept parity (D7):** the removal regex now mirrors Python's embedded-tag guard (`find_vcs_workflow_tag_span`) — a `#` ref counts at text start or after whitespace, so mid-line refs like `fix in #gh:foo now` are removed on accept. Empty `workflow_names` matches nothing (no more `# Heading` deletion). New vectors cover the mid-line case, the empty-names case, and heading lines.
- **LSP accept uses every tag target:** new `build_vcs_project_completion_candidates_with_targets` takes the catalog's `project_tags` (all non-sibling projects plus `home`, including disabled) as the deletion set; the LSP passes `vcs_catalog.project_tags`. The old entries-derived builder remains as a wrapper for existing callers/tests, plus a parity test proving disabled/`home` tags are cleared.
- **Target wire fields (D2):** `ProjectTagTargetWire` gains serde-default `state` and `workspace_dir`; old catalogs still load. Round-trip tests added in core wire tests and the Python binding tests.
- **LSP disabled handling + hover (D3):** disabled targets emit a `disabled_project_tag` warning (`` `+x` is disabled — `sase project enable x` ``) and the `disabled` token modifier; hover and completion docs show `state` and `workspace` when present. New v5-with-state fixture covers disabled/hover/docs/tokens; the old no-state fixture still passes.
- **Rewrite-to-tag:** offers `+x` only when the result is D1-standalone (valid left boundary, end/whitespace/`|`/`}` after), so `#gh:sase.`, `#gh:sase,`, `(#gh:sase)` no longer rewrite. Negative tests added.
- **Suggestions:** full dedupe preserving rank order (fixes `+home, +zome, +home`), with a regression test.
- **Collision warnings (D8):** sibling specs excluded; case-variant directory keys flagged; non-system `Home` keys flagged; `to_lowercase` vs Python `casefold` ASCII-only difference documented; new tests for all three.
- **Dead wire:** the LSP catalog loader now parses through `VcsProjectCatalogWire` (per-field fallback kept for malformed sections, preserving the existing tolerance test).
- **Directive scanning:** left as-is — `directive_scan` has no equivalent leading-token stripper and the frontmatter helpers differ in trim semantics, so it is not a mechanical swap per the plan's own condition.

Verification: targeted suites green (project_tag 23, project_spec 33, vcs_project 15, LSP project_tag 16, catalog 53, wire 117, py bindings 7), then full `sase tool run check` green on re-run (first run hit an unrelated `provider_priority` concurrency load flake that passes in isolation). `sase bead epic-symbols` showed no leftovers before closing.

Declaration accepted for commit. No further work performed this turn.
