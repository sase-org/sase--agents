# Chat History - ace-run (sase-1tc.2)

- **TIMESTAMP:** 2026-11-17 19:04:35 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1tc.2

## Prompt

%auto
#gh:gh_sase-org__sase
%id(2, clan=sase-1tc, bead=sase-1tc.2)
%model:@medium
%w(sase-1tc.1, for_epic=false)
%w(bead=sase-1tc.1)
Can you complete the work for bead sase-1tc.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tc.2` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tc.2` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tc.2 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tc.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tc.2 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tc.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tc.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Phase bead closed.

Done: provider retry no longer re-runs agents for host finalizer failures ([sase-1tc.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-1tc/sase-1tc.2)).

- Added `is_host_finalizer_failure` in [retry_config.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_35/src/sase/llm_provider/retry_config.py): typed chain-walk for `sase.finalizers.*` exceptions plus a text fallback on host-owned phrases (`sase stitch create`, `finalize_commit`, `commit finalizer`, …) that no genuine provider error contains.
- [run_agent_exec_retry.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_35/src/sase/axe/run_agent_exec_retry.py) returns `"raise"` for those failures before retry matching and usage-limit handling, with no wait, no attempt snapshot, and no provider disable.
- Verified: 14 new tests pass; 4 fail on pre-fix code (the genuine-500 guard passes both ways by design); real provider 500s still retry; neighboring retry suites green. `sase tool run check`: all lint gates green, scoped lane 12906 passed with 1 failure that reproduces identically on the clean tree (unrelated TUI marker-audit site, recorded as a follow-up on the bead).

Declaration submitted: commit with bead close for sase-1tc.2.
