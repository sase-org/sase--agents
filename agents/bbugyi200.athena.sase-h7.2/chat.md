# Chat History - ace-run (sase-h7.2)

- **TIMESTAMP:** 2026-08-07 17:48:35 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-h7.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-h7, bead=sase-h7.2)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-h7.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-h7.2 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-h7.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now writing the shared module.

Now wire it into the executor.

Now update the docstring and the surfaces.

Now the broader gate suites and mobile/plan/launch paths.

Now update the tests to use the public entry point.

All changes are in place; waiting on the `just check` gates.

`just check` is still running in the background. I'll report as soon as it finishes.

Now the full gate suites plus lint.

All 1681 gate/notification tests pass. Now the lint gates.

Now resolving the conflict against the new executor structure.

All green after the rebase. Now finalizing the commit.

Bead `sase-h7.2` is closed and the work is committed and pushed (`e18409056`).

**What landed**

`src/sase/notification_gates/feedback_input.py` (new) holds one rule: the reviewer's note is injected as `input.feedback` for a selected option **iff that option's `input_schema` declares a `feedback` property**. Testing `properties` rather than `required` is what makes it work for commands that merely accept an optional note; options that don't declare it are left alone, since many built-ins close their input object with `additionalProperties: false`. The module is labelled a compatibility shim with its deletion trigger (once declarative per-option `inputs` land, `feedback` becomes an ordinary declared field).

The rule is applied inside `execute_gate_selection`, not per surface, so ACE, mobile, Telegram, and headless callers all get it. Surfaces stopped assembling it: the mobile bridge's `"feedback" in selected_option_ids` heuristic and ACE's hardcoded `input_data={}` are gone.

**Built-in schema audit** (done before generalizing): launch and plan feedback options already declare the property, so injection matches what those surfaces assembled by hand; workflow HITL, task triage, and snooze options do not, so their empty-input-asserting commands are untouched. Tests pin all three cases.

**Verification** — new `tests/test_gate_feedback_input.py` (7 tests, including required-feedback failing with `feedback_required` before any command runs) plus a new mobile bridge test; 1470 gate/notification tests pass after the rebase; `just check` was fully green (all lint gates + scoped tests) before the rebase.

**One thing worth flagging:** the commit hit a rebase conflict with sibling phase `sase-h7.1` (executor-integrity), which landed a rejection-recording path, input bounds check, execution journal, and an `_execute_one_option` helper. I resolved it by grafting per-option inputs onto the new structure: `_normalize_feedback` now runs inside a `_recorded_rejection` block *before* input validation (the note must be normalized before it can be injected), input bounds/schema checks and the journal's `input_digests` use the per-option value, and `_execute_one_option` receives it. That reorders `feedback_required` ahead of input-schema rejection; the full gate suite passes with it. Pyright flags a few diagnostics in `executor.py` (line 550 `max` overload, unreachable code) — those are in h7.1's incoming code, not mine, and mypy is the gate this repo enforces.

Telegram's `feedback_is_command_input()` deletion stays scheduled in `sase-h7.8` (inputs-remote), which owns that repo — no follow-up bead needed since it's already tracked there.
