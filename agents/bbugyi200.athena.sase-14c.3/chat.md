# Chat History - ace-run (sase-14c.3)

- **TIMESTAMP:** 2026-09-20 16:05:07 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-14c.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-14c, bead=sase-14c.3)
%model:@small
%auto
%w:sase-14c.2
%w(bead=sase-14c.2)
Can you complete the work for bead sase-14c.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-14c.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14c.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14c.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Editing the shipped default config, schema and docs for the Muse indicator policy. After that I'll add tests and run the render checks.

Now find how existing tests exercise the projection with default config.

Venv is stale (0.34.69, floor is 0.34.70). Running `just install`.

Now the test, modelled on the existing pipeline test.

Tests pass. Now the docs.

Render check: render the real projection through the indicator at 60, 80 and 140 columns, in dark and light.

The Muse group renders correctly in both themes and degrades cleanly on narrow budgets. I'll pin it with a real-header test at 60, 80 and 140 columns.

Now the live exercise against the real Muse binary.

Live refresh landed both windows. Now the real projection with shipped config, then `just check`.

Two things to check: Muse is absent from the live projection, and the flag-lint failure looks unrelated.

Seven failures, none in usage or config code. I'll rerun them to see whether they're flaky.

Those 7 fail identically on a clean tree, so they're pre-existing. I'll run the lint gates that come after the failing flags gate.

The remaining failures (symvision stale `sase-14d.4` entries, flags `sase-12m`, 7 epic-panel/capacity tests) are all pre-existing and unrelated. I'll record them as follow-ups and close.

I already closed the bead, so the host can't take a `close` action on it. I'll resubmit with `keep`.

Bead sase-14c.3 is done and closed. Muse's weekly window now shows in the TUI header by default and its 5-hour window is hidden.

**What changed**
- `src/sase/default_config.yml` and the `src/sase/config/sase.schema.json` default now set `muse` `windows.session: never` under the indicator providers. The weekly window needs no entry because the existing `weekly_all: always` policy already selects it.
- `docs/configuration.md` and `docs/llms.md` document the policy and the one-line config that brings the 5-hour window back.
- No layout code changed, so no PNG goldens changed.

**Tests added**
- The shipped defaults select Muse's weekly window and hide the `session` window even at 12% left.
- Without the override, the generic fallback shows `session` again.
- With no `muse` binary on `PATH`, Muse is not eligible and the projection is empty.
- The real header renders correctly at 60, 80 and 140 columns. The `♾️` badge and `97%` show, and the 5-hour figure never does.

**Verification**
- I rendered the indicator in dark and light themes. It shows `♾️ 97% 4d15h` and collapses cleanly at narrow widths.
- `sase usage refresh -p muse` against the real Muse binary landed both windows through the probe, and `sase usage list` shows them.
- Muse doesn't appear in this host's live header yet. No model alias references it and it isn't explicitly enabled, so it isn't eligible. That is the existing "installed and in use" rule.
- `just check` does not pass. ruff, mypy, fmt and keep-sorted pass. The failures that stop it are unrelated to this bead:
  - The feature-flag lint fails on a closed `sase-12m` flag.
  - The symvision lint fails on stale `sase-14d.4` entries.
  - Seven tests in `test_capacity_gate_to_admission.py`, `test_epic_panel_arrival_frames.py` and `test_lazy_tier2_reconcile_apply.py` fail the same way on a clean tree.
- I recorded those failures as a `PROPOSED FOLLOW-UP:` note on the bead.

I closed the bead myself, so the final declaration used `keep` for the bead action. The host refused `close` on an already-closed bead.
