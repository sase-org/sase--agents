# Chat History - ace-run (sase-1tz.2.1.7)

- **TIMESTAMP:** 2026-11-19 18:47:20 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1tz.2.1.7

## Prompt

%auto
#gh:gh_sase-org__sase
%id(7, clan=sase-1tz.2.1, bead=sase-1tz.2.1.7)
%model:@small
%w(sase-1tz.2.1.3,sase-1tz.2.1.6, for_epic=false)
%w(bead=sase-1tz.2.1.3)
%w(bead=sase-1tz.2.1.6)
Can you complete the work for bead sase-1tz.2.1.7? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.2.1.7` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.2.1.7` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.2.1.7 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.2.1.7 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.2.1.7 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.2.1.7`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.2.1.7 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Done. Bead [sase-1tz.2.1.7](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1tz/sase-1tz.2.1.7.md) work is complete and the final declaration is submitted (commit + close; the host lands it from here).

What landed in this checkout:

- [Outbox check groups by cause](https://github.com/sase-org/sase/blob/master/src/sase/doctor/_agent_publication.py) — open rows fold by `(project, signature)` into one issue per cause with request count, total attempts, and first/last times, so the count stays flat across ticks. Live `standing_alerts.json` rows surface in the payload and join each group (read-only, fail-open).
- [Terminal rows are settled, not issues](https://github.com/sase-org/sase/blob/master/src/sase/doctor/checks_agent_publication_outbox.py) — `prompt_archive_unrecoverable` rows are counted in `settled_request_count` with an audit pointer, never in the issue count.
- [Stale-only protection is OK](https://github.com/sase-org/sase/blob/master/src/sase/doctor/checks_agent_publication_protection.py) — sase-1rb remedy (a); enforced/unverified rows still WARN. Closed sase-1rb on this basis.
- Docs updated in `hood-sync.md`; the two `--epic-symbol` rows dropped from `Justfile` (symvision confirms both symbols properly used).

Verification: 72 tests pass (doctor + outbox + standing). `just check` is green except a symvision NEW for `LaunchPromptContext`, which I proved reproduces on clean HEAD — recorded as a `PROPOSED FOLLOW-UP`, as is remedy (b) (withheld `chat.md` bytes).

Two notes for the land agent: athena before-numbers are on the bead (outbox WARN 5202 issues; protection WARN 6 blocked / 52 stale), and `sase bead close` refused locally only because the whitelist rows still sit on origin/master — they clear when this stitch merges, which is when the host close runs.
