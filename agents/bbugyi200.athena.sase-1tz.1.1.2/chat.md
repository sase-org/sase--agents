# Chat History - ace-run (sase-1tz.1.1.2)

- **TIMESTAMP:** 2026-11-19 09:59:54 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1tz.1.1.2

## Prompt

%auto
#gh:gh_sase-org__sase
%id(2, clan=sase-1tz.1.1, bead=sase-1tz.1.1.2)
%model:@medium
%w(sase-1tz.1.1.1, for_epic=false)
%w(bead=sase-1tz.1.1.1)
Can you complete the work for bead sase-1tz.1.1.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.1.1.2` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.1.1.2` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.1.1.2 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.1.1.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.1.1.2 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.1.1.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.1.1.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Done. Bead `sase-1tz.1.1.2` (held_settle) is complete, verified, and closed, with the final declaration accepted.

What was built: retention records now persist an evidence fingerprint (policy reason, dirt classification, affected repos, normalized probe errors, per-repo dirty-path sets) plus a cheap no-subprocess stat signature (gitdir `index`/`HEAD`/resolved branch-ref and checkout-root mtimes via new `src/sase/turns/_workspace_retention/evidence.py`) and `probed_at`. Unchanged cleanup passes skip all git probes, snapshots, decision-sheet publishing, pins, record writes, and +1s; changed evidence re-settles with exactly one +1 naming the change; undismissed rows get at most one hourly still-held heartbeat; dismissed rows latch with no resurrection after compaction. The per-pass "retained with other dirt" log now fires only on change, with one skip-summary line per pass.

Verification: 7 new tests in `tests/test_held_settle_evidence.py` pass; the 3 existing tests encoding always-resettle were updated to the new semantics; related suites (monitor retention, stale cleanup, hijack, chop triggers — 260+ tests) pass. Repo-wide mypy, ruff, symvision, toobig, keep-sorted, docs-lint, and epic-symbol freshness are clean. `just check`'s `_setup` validator fails identically on the clean tree (linked sase-core already carries the sibling `unknown_sizes` phase's wire v2 against this checkout's pin) — recorded as a `PROPOSED FOLLOW-UP:` on the bead. Before-numbers (athena store ~20 generations/min on a 7.3 MB file) and the after-install repeat command are noted on the bead and on `sase-1tz.1`.
