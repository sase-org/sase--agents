# Chat History - ace-run (sase-16y.1)

- **TIMESTAMP:** 2026-09-23 11:38:55 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16y.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-16y.1, bead=sase-16y.1)
%clan(sase-16y, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-16y.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16y.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16y.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16y.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16y.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16y.1 (legend phase) is done and closed.

What landed, all presentation-only with no visible change:

- Model ([_member_roster.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/ace/tui/widgets/prompt_panel/_member_roster.py)): `MemberJumpSection` plus per-target `label`/`status_bucket` on `MemberJumpMap`, section recording in `append_member_roster()` (including the zero-numbered capacity-spent case), section concatenation in `merged_member_jump_map()`, and a public `member_status_style()` helper.
- Carrier: `member_jump_map` slot + `with_member_jump_map()` on `AgentHeaderRenderable` (digest- and render-neutral), shared carrier walker behind `find_identity_header()`, plus new `find_member_jump_map()` and `MemberJumpMapSink`.
- Builders: detached header/clan/tribe paths attach the exact object they publish (verified with `is`); no map for hint-mode, tribe cheap, member-less clan, or non-roster documents. Group/`.renderable` wrapping (family, proc-shell, hint renderables) preserves the map via the walker.
- Plumbing: `AgentPromptPanel.attach_member_jump_map_sink()` fires right after the identity sink, before the digest early return.
- Renderer ([_agent_jump_legend.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/src/sase/ace/tui/widgets/_agent_jump_legend.py)): `JumpLegendRenderable` with collapsed (≤2 rows, uniqueness-preserving packer, `+K` overflow, `MIN_LABEL_CELLS=10`, middle-ellipsis, cell-based measuring), expanded (full labels, headings for ≥2 sections, tails, `revive`), and narrowed modes, plus `jump_legend_title()` / `jump_legend_border_accent()` and a width-independent content digest. Layout memoized per width; no I/O.

Verification: 50 new tests pass ([sections](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/tests/ace/tui/widgets/test_member_jump_sections.py), [legend](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_39/tests/ace/tui/widgets/test_agent_jump_legend.py)); neighboring suites (roster, identity header, tribe, lane neighbors, fold contracts, digest) green; ruff/mypy/keep-sorted green. One existing test needed a faithful update: the clan launch-order test asserted full target equality across status churn, which contradicts the mandated `status_bucket` enrichment, so it now compares order-stable fields and asserts the churned buckets. Four new public symbols are whitelisted via `--epic-symbol sase-16y(...)` for the panel phase to consume; `epic-symbols sase-16y.1` is clean. No rendering path changed, so PNG goldens are untouched.

Caveats for the land agent: `just check` is red on pre-existing gates unrelated to this work — pyscripts tools/visual placement, symvision `ExpandedLaunchSegments`, and ~13 scoped failures in bead CLI/prompt/query areas (two proven pre-existing by re-running with my changes stashed). Recorded as a `PROPOSED FOLLOW-UP` note on the bead.
