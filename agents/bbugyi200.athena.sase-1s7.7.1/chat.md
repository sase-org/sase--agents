# Chat History - ace-run (sase-1s7.7.1)

- **TIMESTAMP:** 2026-11-11 03:45:36 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1s7.7.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-1s7.7.1, bead=sase-1s7.7.1)
%clan(sase-1s7.7, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-1s7.7.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1s7.7.1` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1s7.7.1` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1s7.7.1 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1s7.7.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1s7.7.1 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1s7.7.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1s7.7.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead sase-1s7.7.1 (train-fixes) is done and declared.

- `tools/_release_watch_facts.py`: `pin_changed` now means only the source pin differs from master's; dropped the exact-pin comparison and the `master_core_pin` read. `exact_public_core_pin` stays in the facts for the Rust policy.
- `.github/workflows/publish.yml`: the sync job runs `python tools/render_applicability` after `uv lock` and carries `docs/overrides/generated/release_announce.html` through the diff check and `git add`. Verified on a scratch checkout of the release branch (manifest 0.19.0, partial stale at v0.18.1) that this renderer is the only version-bump-stale one.
- `.github/workflows/release.yml`: `publish` and `confirm` gained `setup-uv` with cache options after checkout. Audit: all other `uv`-invoking jobs already had it; `stash`/`exercise`/`qualify` jobs need only preinstalled `python3`/`gh`/`curl`.
- Tests: new `FakePrGithub` contract cases plus a collector module with an end-to-end decision proof (drifted exact pin matching core-ensure's pick reaches `releasable`, merge proposed-not-executed); workflow audit tests for both YAMLs; a stale-partial render round-trip test. Each new test was proven to fail pre-fix.
- Docs: two sentences in `docs/contribute/release-train.md`, within budget.

`sase tool run check` passed, `just toobig` clean, `epic-symbols` empty, bead closed, final declaration accepted.
