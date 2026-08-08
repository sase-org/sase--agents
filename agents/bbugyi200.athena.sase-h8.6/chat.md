# Chat History - ace-run (sase-h8.6)

- **TIMESTAMP:** 2026-08-07 22:50:10 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-h8.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-h8, bead=sase-h8.6)
%model:@medium_phase_worker
%auto
%w:sase-h8.3
%w(bead=sase-h8.2)
%w(bead=sase-h8.3)
Can you complete the work for bead sase-h8.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-h8.6 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-h8.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Let me establish a pre-fix baseline under the contention harness.

Confirmed the mechanism. Now let me implement the fix in the testing DSL.

Now update the tests to use it.

Now let me confirm the new guard test actually fails without the pin.

The earlier soak was contaminated by my own falsification edit (pin disabled during repeats 2–4). Running a clean post-fix soak now, with no concurrent edits.

Verification is complete. Recording findings on the bead.

Bead `sase-h8.6` is complete and closed.

## What the flake actually was

Confirmed by probe, not inference: `_set_prompt_text` waited for the detail debouncer to be idle, wrote the corpus, then did one bare `pause()`. Any repaint scheduled *after* that idle check — the debounced detail update, the immediate header path, the async header-enrichment message, the slow-tool tick — lands inside the pause and re-derives the panel document from the real agent. `/` then captures a corpus with no match, so `current_selection` is `None` and the overlay renders empty.

## The fix

`src/sase/ace/testing/prompt_document.py` — a published, documented helper `set_agent_prompt_document(page, content)` that suppresses the competing render rather than racing or retrying it: it installs a one-way gate on that panel instance's `update`, so the app can no longer re-derive the document, and then settle-verifies its own write with a bounded wait. Re-calling it replaces the pinned document, which is how `test_inline_metadata_search_yank_and_frozen_refresh` now simulates a background refresh under a frozen overlay.

The three F3 nodes moved onto it, plus a new guard node `test_pinned_metadata_document_survives_a_debounced_repaint`.

## Measurements

| | result |
|---|---|
| Pre-fix soak (6 repeats, 26 workers on 2 CPUs) | 4/6, 3/6, 3/6 — red repeats 3,4,5,6 |
| Post-fix soak (same + `test_artifacts_files_detail.py`) | 0 nodes failed, 585.3s, red repeats none |
| Guard node with the pin disabled | fails serially and deterministically in 2.1s |

`just lint` green. `just check-full`: 27440 passed, 7 failures — all pre-existing: the six known X1 gate nodes from `ff0b765a4`, plus `tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand`, which I verified also fails on a stashed clean tree.

The F4 half (`test_rapid_navigation_loads_only_the_final_detail`) needed no work — it already fakes `set_timer` and asserts on the last callback, is absent from the health store's flake set, and was 0/6 in the post-fix soak. The epic plan overstated that membership; the sase-h8.3 triage table is right.

Two `PROPOSED FOLLOW-UP:` notes are on the bead for the land agent: the doctor-test regression, and extending the phase-`gate` lint check to flag raw injections into app-derived ACE panels. Changes are left uncommitted in the workspace tree.

Bead is already closed. Re-running the close to verify it was published:

Close is published (no unpublished diagnostic). Now committing:

Working tree clean, branch level with `origin/master`.

**Bead `sase-h8.6`** — the close was already published (re-running `sase bead close` reported `Already closed` and exited cleanly, with no unpublished diagnostic); I added the verification note to it.

**Committed** (`test(ace): pin the metadata-search corpus against competing repaints`):
- `src/sase/ace/testing/prompt_document.py` (new) — `set_agent_prompt_document(page, content)`, which gates the panel instance's `update` one-way so the app can't re-derive the document, then settle-verifies its own write under a bounded wait.
- `src/sase/ace/testing/__init__.py` — export the helper.
- `tests/ace/tui/test_agent_metadata_search.py` — three F3 nodes moved onto the helper, plus the new guard node `test_pinned_metadata_document_survives_a_debounced_repaint`.

Verification carried over from the work pass: pre-fix soak red on repeats 3–6 (26 workers / 2 CPUs), post-fix soak 0 failing nodes over 6 repeats (585.3s), guard node fails deterministically with the pin disabled, `just lint` green, and the `just check-full` failures were all confirmed pre-existing.
