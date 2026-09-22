# Chat History - ace-run (sase-16h.5)

- **TIMESTAMP:** 2026-09-22 18:00:08 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16h.5

## Prompt

#gh:gh_sase-org__sase
%id(5, clan=sase-16h, bead=sase-16h.5)
%model:@medium
%auto
%w:sase-16h.4
%w(bead=sase-16h.4)
Can you complete the work for bead sase-16h.5? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16h.5 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16h.5 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16h.5`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16h.5 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16h.5 is closed. The follow-up note landed as well.

Done: monitor-wrap phase implemented and verified.

- New `src/sase/monitor/tool_wrap.py` decides the proc argv: host-owned `execution_argv` launches and single `sase tool run` commands pass through byte-identical; a simple command matching a catalog entry at the monitor cwd's project root upgrades to a named `sase tool run <name>` (extra args only with `args: allow`); everything else under `-p verify` (or under `all` regardless of profile) wraps ad-hoc as `sase tool run -- /bin/sh -c CMD`. Simple means no operators, redirects, globs, expansions, or leading `NAME=value`, so the named form always runs identically to the raw command.
- Only the supervisor-exec'd argv changes. `monitor_command` and `monitor_execution_argv` stay byte-identical, so `-f` completion keeps resolving the raw command. The wrapper is built from `sys.executable -m sase`, and the catalog resolves against the monitor's cwd, not the starter's.
- New `monitor.tool_wrap` (`off | verify | all`, default `verify`) in `default_config.yml` and the schema, read through a fail-open `get_monitor_tool_wrap` accessor. `SASE_TOOL_BYPASS` and catalog failures run raw with exactly one `sase: running unwrapped (<reason>)` line at the top of the monitor log.
- Docs: policy table in `docs/monitors.md`, cross-reference in `docs/tool.md`; skill source updated (plain `-- just check` now equivalent, bypass fallback). Skill preview shows nothing to deploy from here.

Verification: 24 tests in `tests/monitor/test_monitor_tool_wrap.py` pass, including a live named run recording `owner_kind=monitor` with the promoted starter attributed, single ad-hoc runs, no re-wrap, and auto evidence selecting the tail through the wrapper header/footer. Full `tests/monitor/` (364), `tests/tool/`, and config/schema suites pass; ruff, mypy, and symvision are clean for all touched symbols.

Two findings, both out of scope and recorded: `just check` stays red only on a pre-existing symvision flag for `delete_paths_in_background` (a file this phase never touched; filed as `PROPOSED FOLLOW-UP` on the bead for the land agent), and live timeout/failure monitor settlement hangs in sandboxes because recovery-followup launch has no agent runner there — raw and wrapped monitors behave identically.

Declaration accepted for the commit payload (bead already closed, so submitted with keep). No further work done.
