# Chat History - ace-run (sase-1le.3)

- **TIMESTAMP:** 2026-10-15 19:06:04 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1le.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-1le, bead=sase-1le.3)
%model:@small
%auto
Can you complete the work for bead sase-1le.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1le.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1le.3 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1le.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1le.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead sase-1le.3 is done and closed.

What landed (floor branch, per the epic decisions):

- **Single-sourced install command** — new `tools/render_applicability` owns `INSTALL_COMMAND = 'uv tool install "sase>=0.18"'`, with `--install-command` (read by the smoke workflow), `--check-installed` (asserts `sase version -j` meets the floor), and `--check` (verifies the generated partial plus command containment in all five docs). Applied the floor to every copy-pasteable install fence in `README.md`, `INSTALL.md`, `docs/getting_started.md`, `docs/plugins.md`, and `docs/rust_backend.md`.
- **Release line** — dismissible Material announce banner via `docs/overrides/main.html` plus `announce.dismiss`, rendered from `.release-please-manifest.json` into a generated partial. Since the manifest reads 0.17.1 (below the floor), it truthfully says "v0.18 pending — the documented install is not yet released". Hidden from the handbook PDF via the `extra.pdf_handbook` guard.
- **Scheduled smoke** — new `.github/workflows/install-smoke.yml` (daily cron + dispatch): runs the single-sourced command on clean Ubuntu, asserts the floor, then `sase --help` and `sase doctor -j` (warnings tolerated, hard errors fail).
- **Drift check + tests** — wired into `fmt-docs`/`fmt-docs-check`; new `tests/test_render_applicability.py` (7 tests).

Verification: strict docs build green with the banner confirmed in the rendered HTML; PyPI resolution checked live — max available is 0.17.1, so the floor command fails loudly (`only sase<=0.17.1 is available`) instead of silently installing 0.1.0, and the smoke will report that red until 0.18 ships. Full `just check`: all lint stages and 55,905 scoped tests passed except one sandbox test broken by my new Justfile line — root-caused, sandbox extended, all 22 tests in both affected files green on re-run. No epic-symbol entries. Two follow-ups recorded on the bead as notes (dated blog-post fences; a pre-existing `doctor` macro error in this checkout). Final declaration accepted with `bead_action: close`.
