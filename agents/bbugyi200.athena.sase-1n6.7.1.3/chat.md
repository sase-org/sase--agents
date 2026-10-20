# Chat History - ace-run (sase-1n6.7.1.3)

- **TIMESTAMP:** 2026-10-20 00:12:38 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1n6.7.1.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-1n6.7.1, bead=sase-1n6.7.1.3)
%model:@medium
%auto
%w(sase-1n6.7.1.1,sase-1n6.7.1.2, for_epic=false)
%w(bead=sase-1n6.7.1.1)
%w(bead=sase-1n6.7.1.2)
Can you complete the work for bead sase-1n6.7.1.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Check
whether the earlier work landed before redoing anything, and run `sase bead open sase-1n6.7.1.3` only if the work
is genuinely unfinished. Read its
description and design file with `sase bead read sase-1n6.7.1.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1n6.7.1.3 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1n6.7.1.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1n6.7.1.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Phase bead `sase-1n6.7.1.3` (health-facts) is done and closed.

What landed:
- [New health reader](tools/_release_watch_health.py) — `ReleaseHealthReader` covering `core` (core master CI, open release-plz PR, core-cut runs with typed `CORE_CUT_RED`/`CHECKS_NEVER_REGISTERED` annotation evidence), `canary` (newest scheduled install-smoke results, green→pass normalization, missing/corrupt→findings), `core_ensure` (via shared `ensure_core` on fresh PyPI + PR-head/master pin), `issues` (open+closed steward issues with marker parsing), `core_actions_access` (read-only probe), and `blocker_lineage` (oldest open marker).
- [Snapshot composition](tools/_release_watch_facts.py) — `collect_snapshot()` merges train + health thirds into the full 16-key wire, plus three small public accessors.
- [37 tests](tests/test_release_watch_health.py) including a real `sase_core_rs` binding round trip (exit 0, `nothing_to_release`) and regression tests for three latent train-reader bugs I proved against the live API and fixed minimally (`_git_file` base64 wrapping, `_pages` array flattening, repository trailing slash). Existing suites still pass.
- `sase tool run check` green (run `f649092a`); no `--epic-symbol` entries.

Two out-of-scope findings recorded as `PROPOSED FOLLOW-UP:` notes: year-long paginated histories exceed the 20s transport timeout live, and expected checks are unreadable because sase master uses the `master-integrity` ruleset rather than legacy branch protection. Index holds intent-to-add entries for the two new files so the pyscripts gate can see them; nothing committed.

Declaration accepted for `commit` with bead close. Work preserved for host commit.
