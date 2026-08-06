# Chat History - ace-run (sase-g3.3)

- **TIMESTAMP:** 2026-08-06 10:29:42 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-g3.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-g3, bead=sase-g3.3)
%model:@medium_phase_worker
%auto
%w:sase-g3.1
%w(bead=sase-g3.1)
Can you complete the work for bead sase-g3.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-g3.3 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-g3.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now the contexts `usable` property:

Now restructure `select_tests`:

Now the imports and manifest field:

Now let me check the depth-2 vs depth-3 backtest results:

Now update the manifest field test:

Now the new tests for the compensation:

Now add the compensation tests:

Now check whether the `test_plan_display` failure is pre-existing:

Now recording the follow-ups and closing the bead:

Phase `compensate` (sase-g3.3) is done and the bead is closed.

## What shipped

`no-baseline-depth-boost` — a named rule that fires when the coverage-contexts baseline is missing or stale. Instead of escalating (forbidden by the plan, and it would send ~half the lane to the full suite), the reverse-import closure walks **one hop deeper**.

- `tests/_test_selection.py:288` — contexts are now consulted *before* the closure, because baseline status decides the depth; manifest gained `effective_depth` (schema 2 → 3)
- `tests/_test_selection_rules.py` — the rule, with a comment stating why it is deliberately not in `FULL_SUITE_RULES`
- `tests/_test_selection_contexts.py` — `ContextSelection.usable`
- Five new tests pin the rule, its composition with the rename/delete hop, and that it never escalates. Fixture tests that assert closure depth now install a *fresh* baseline so they measure the closure, not the compensation.

## Measured, not assumed

Backtest over 63 commits with usable ground truth (`--baseline 96183d71b` at `4651ed199`), closure-only arm:

| | mean recall | p10 | worst | blind-spot commits | missed files | median selection |
|---|---:|---:|---:|---:|---:|---:|
| before | 96.0% | 85.3% | 23.5% | 13/63 | 116 | 6.4% |
| after | 99.2% | 100% | 81.3% | 5/63 | 11 | 8.8% |

Re-running the backtest *after* the change reproduces those numbers through the real code path, with the union arm (baseline present) unchanged — so the boost applies only when there is no usable baseline. Cost is roughly double the selected files when uncached (`agent_lanes.py`: 110 → 255 files, 57s → 164s serial); the median scoped run (contract-set-only, 34 files) is untouched.

On the plan's sharpest case, a real edit in `_app_layout.py`'s `compose` body recovers 27 of the 69 missed covering test files (recall 24.2% → 53.8%) at 14.2% of the suite. Candidate 2 (directory-mirror) was measured and rejected: `tests/ace/tui/**` is 35.7% of the suite, so it degenerates into a full run.

## Verification

160 targeted tests pass; `just lint` clean; `just check-full` green except two failures unrelated to this change — `test_plan_display.py::test_malformed_header_block_leaves_authored_metadata_visible` reproduces on a stashed clean tree, and one ACE TUI test passes in isolation and in an earlier full run of the same tree (known load-sensitive flake family). Both, plus three more discoveries (the backtest silently reporting a null result outside the venv; thin local baselines outranking fuller CI ones by mtime; the residual `_app_layout.py` shape), are recorded as `PROPOSED FOLLOW-UP:` notes for the land agent.

Changes are in the working tree, uncommitted.

Committed and pushed; working tree clean, branch level with `origin/master`.

**Bead** — `sase bead close sase-g3.3` reported `Already closed` (closed earlier in the run, published) and recorded the verification note.

**Commit** — `feat(test-selection): walk one hop deeper when no contexts baseline is usable`, covering all nine listed files.

The change: when the coverage-contexts baseline is missing or stale, the reverse-import closure walks one hop deeper and records a named `no-baseline-depth-boost` rule, rather than escalating to the full suite (which would fire on roughly half of scoped runs). Contexts are consulted before the closure since baseline status decides depth; the manifest gained `effective_depth` (schema 2 → 3). Backtest over 63 commits, closure-only arm: mean recall 96.0% → 99.2%, worst 23.5% → 81.3%, blind-spot commits 13 → 5, median selection 6.4% → 8.8%; the baseline-present arm is unchanged.

Two `just check-full` failures noted in the earlier pass were unrelated to this change (one reproduces on a stashed clean tree, one is a known load-sensitive ACE TUI flake); both, plus three other discoveries, are recorded as `PROPOSED FOLLOW-UP:` notes on the bead for the land agent.
