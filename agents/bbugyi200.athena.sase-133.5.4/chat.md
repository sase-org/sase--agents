# Chat History - ace-run (sase-133.5.4)

- **TIMESTAMP:** 2026-09-20 11:33:08 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-133.5.4

## Prompt

%id(4, clan=sase-133.5, bead=sase-133.5.4)
#gh:gh_sase-org__sase
%model:@medium
%auto
%w:sase-133.5.2,sase-133.5.3
%w(bead=sase-133.5.2)
%w(bead=sase-133.5.3)
Can you complete the work for bead sase-133.5.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-133.5.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-133.5.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-133.5.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Now a live comparison script: owner loader run on apollo, catalog projection fetched from athena.

Owner and viewer still differ in family `×N` counts, shell chips (`⚙N`), and done-history depth. I'm checking the raw catalog rows to separate real bugs from bounded-window differences.

Add a gateway-level test for the production root-less completed family right after the "root represents members" test.

Core `just check` is green (exit 0). Now rebuilding the binding in the workspace venv and re-running the Python oracles against the anchor-based rule.

Fix built; I'm replaying apollo's real data through the fixed extension from a temp directory (apollo's installed build untouched).

Now the fixed-clock visual test derived from the real assembled catalog of the production fixture.

Deterministic now; golden created. Inspecting the PNG.

Checking what the three drifted goldens changed (baseline drift vs. something I caused).

Now recording the evidence and handoff on the bead.

Phase sase-133.5.4 is not complete, and I left the bead open: I couldn't capture a live apollo-versus-viewer comparison on builds that include the fix. I did find and fix why the live views disagreed.

**What the live captures showed**
- Both hosts already ran the same build (sase 0.17.1+957.g6087c0a8e, sase-core-rs 0.34.67), and `sase machine status apollo` reported fleet contract v5 with no version skew.
- The viewer (athena, filtered to `machine:apollo`) still differed from apollo's own TUI. It was missing every completed family made only of shells (`sase-12y.2`, `sase-12o.land`, `sase-zr.7.1`, and others), so the family counts, shell chips and done rows were off. Saved as artifacts: owner `file:explicit:0fabc9428a2dc8170edcfb5a`, viewer `file:explicit:6881b918e8940383cbaa09e7`.

**Cause and fix**
- Modern plan-chain families have no separate root record; the `--plan` shell is the root and has no parent. The sase-core presentation policy dropped terminal shells unless a non-shell root record was present, so completed families vanished. The earlier test fixtures always wrote a synthetic root record, which hid this.
- A second bug: an artifact directory holding only a side file was served as a permanent RUNNING row that the owner loader never builds.
- Fix in sase-core: a parentless shell now presents its family inside the 7-day window, and records with no lifecycle marker are excluded. Shells whose parent no record supplies stay excluded, so the gateway orphan test still passes. sase-core `just check` passes.
- Replaying apollo's real data through the fixed build, from a temp directory so apollo's install was untouched: the catalog serves all 84 named owner identities (31 before) with none extra.
  - Visible nodes are 11 on both sides.
  - The only owner-side rows the catalog lacks are the unnamed workflow step rows.

**Tests**
- The parity fixture now models the production shape, the roster oracle compares rows projected through the viewer, and I added a fixed-clock visual snapshot built from the real assembled catalog (artifact `file:explicit:5ce90c912a66753c9dc58aa7`).
- The parity oracle tests pass (33), and the focused set passes (56).
- The scoped lane passes except 4 known failures unrelated to my files. `just check` itself stops at 20 mypy errors in `ace_tmux*.py`, which was already red before my changes.
- I did not run `just check-full`; no rendering source changed and `just check` is red at baseline.

**Left for someone else** (written on the bead)
- Land the two commits and let sase-core release.
- Run the normal update flow on athena and apollo, restart gateway/AXE, then recapture both views at the same pane size. The owner list is viewport-bounded (19 agents at 120x40, 37 at 150x110), so the sizes must match.
- Three existing fleet goldens drift on the untouched tree; I didn't regenerate them.
- Remote `×N` counts and a few row markers still differ because workflow steps aren't served.
- Apollo's real `~/.sase` holds test-looking `lane--gate` leftovers.

The primary repo and sase-core changes were submitted as commit declarations with the bead action `keep`.
