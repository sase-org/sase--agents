# Chat History - ace-run (sase-1n6.2)

- **TIMESTAMP:** 2026-10-19 17:41:15 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1n6.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-1n6, bead=sase-1n6.2)
%model:@medium
%auto
Can you complete the work for bead sase-1n6.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Check
whether the earlier work landed before redoing anything, and run `sase bead open sase-1n6.2` only if the work
is genuinely unfinished. Read its
description and design file with `sase bead read sase-1n6.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1n6.2 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1n6.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1n6.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead sase-1n6.2 (exact-build) is complete and closed: `release.yml` builds once at the tag and seals the candidate manifest.

What landed in this checkout (host commits after the turn; final declaration accepted):

- [`.github/workflows/release.yml`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.github/workflows/release.yml) — `workflow_dispatch` only (`mode` release/resume/rehearse, rehearse-only `core_version` override, `rebuild` flag). Jobs `identity` (tag/SHA/pyproject/`__version__` agreement), `build` (`uv build`, `twine check`, exactly one wheel + one sdist, core pin resolution, PyPI file-list fetch with `uv.lock` cross-check, seal + verify), `stash` (draft-release only, second-generation refusal), and `not-yet-qualified` (release/resume stop red until later phases land). Concurrency `release-${{ github.ref }}`, no cancel, no push/schedule triggers.
- [`tools/release_candidate`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tools/release_candidate) — `seal`, `verify`, `observe`, `show`, `evaluate`, `download`, plus `core-files` and `core-suffixes`. Candidate ID derives from sealed fields only; incomplete core sets, wrong dist sets, and identity mismatches refuse; missing qualification/exercise evidence evaluates red.
- [`docs/contribute/release-train.md`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/docs/contribute/release-train.md) plus nav, generated docs map, and `llms.txt`.
- Tests: [`tests/test_release_candidate.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_release_candidate.py) and [`tests/test_github_actions_release.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/test_github_actions_release.py) (22 tests, all pass), loader additions, and a contract-set re-curation to 79 entries with measured cost.
- Release-please draft verification: action v5 (lib 17.11.2) honors `draft:true` + `force-tag-creation:true` together — tag created at once, next run finds the previous release via tag scan. Evidence recorded on the bead; no fallback needed.
- Human gate raised for the trusted publisher and `v*` tag rule: `custom-1ab2c0b9-6768-4c64-8568-bc686a0e514c` (ID noted on the bead for `sase gate show`).

Verification: `sase tool run check` run `07b9835b8dfab6b46be4b7d7306f250f` — all lint gates green, 56703 scoped tests passed. Four failures triaged: the contract-budget one fixed by the sanctioned re-curation; one load flake green in isolation; two `test_parser_stats` golden failures reproduce identically on the clean base tree, recorded as `PROPOSED FOLLOW-UP` on the bead, and the bead closed per the phase rule. Live `rehearse` dispatch 422s because `release.yml` is not on `master` yet (expected under the tag-frozen-workflow rule); a local seal/verify/evaluate proof against real repo state passed instead, and the post-landing rehearsal belongs to a later phase.
