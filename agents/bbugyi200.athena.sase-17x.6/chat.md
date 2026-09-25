# Chat History - ace-run (sase-17x.6)

- **TIMESTAMP:** 2026-09-24 12:54:24 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17x.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-17x, bead=sase-17x.6)
%model:@medium
%auto
%w:sase-17x.4
%w(bead=sase-17x.4)
Can you complete the work for bead sase-17x.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17x.6 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17x.6 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17x.6`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17x.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-17x.6 (Command-line proc plumbing) is complete and closed.

What landed:
- `submit_command_line_proc` in [command_line.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/procs/command_line.py) — tagged ordinary proc with the output env contract (`PYTHONUNBUFFERED`, `FORCE_COLOR`, `COLUMNS`), no operation/service/concurrency keys; producer site `command-line.submit` registered.
- Observer exit watch (`register_exit_watch` → `ProcExitCompletion` from store `status`/`exit_code`/`finished_at`, no typed-result decode) and ref-counted tail subscriptions (`subscribe_tail`/`unsubscribe_tail`); `set_detail_proc` kept as a shim since test fakes depend on it, both in-repo callers migrated.
- `ProcLogCursor` in [logs.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/procs/logs.py) — `(inode, offset)` incremental reads with per-read cap, rotation/truncation recovery via `.log.1`, `lost_bytes` reporting.
- `ObservedProc.tags` plumbed from store rows; Procs `tag:`/`origin:` query fields with adapter and [docs/ace.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/docs/ace.md) updates.
- `proc_focus_target` threaded from `_open_config_center` through `ConfigCenterModal` into `ProcsPane.focus_proc_target`, which clears a hiding filter with a notice.

Verification: 182 focused + 217 related tests green, ruff + mypy clean, no symvision findings in touched files, `epic-symbols` clean. Final declaration accepted.
