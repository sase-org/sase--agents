# Chat History - ace-run (sase-1if.2)

- **TIMESTAMP:** 2026-10-08 15:56:02 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1if.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-1if, bead=sase-1if.2)
%model:@medium
%auto
Can you complete the work for bead sase-1if.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1if.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1if.2 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1if.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1if.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open.

## Response

Bead sase-1if.2 (listen-adapter) is done and closed.

What landed in the sase-listen checkout (uncommitted; host commits it):

- `sase_commands` entry point (`listen = "sase_listen.sase_command"`) plus a stdlib-only `sase_command.py` adapter (`SASE_COMMAND_API = 1`, `SUMMARY`, lazy `main`/`build_parser` delegation) and a new `invocation.py` leaf module for the invoked program name.
- Program-name threading: `prog` params on `cli.main`, `app.main`/`build_parser`, and all 11 command modules; epilogs, error prefixes, "run this next" hints, stale-env messages, the starter-config comment, and the guide `{{ prog }}` token all follow the invoked name. Product/distribution names, `--version`, XDG paths, the audited-read reason, and wire strings stay `sase-listen`.
- `buildinfo.upgrade_command()` returns `sase plugin update listen` when the uv receipt's first requirement is `sase`; doctor hints follow automatically.
- Feed host: remote shell tries `sase-listen`, then `sase listen`, else exit 127 mapped to an install hint; too-old detection tightened to `invalid choice: 'receive'`.
- Deleted dead `src/sase_listen/cli.py`; rewrote the standalone stance in AGENTS.md, CONTRIBUTING.md, README.md, and 7 docs pages (background notes the superseded plan decision); `sase_completion = "path"` on the 9 path-like slots via `invocation.mark_path_completion`.
- Tests: new `test_sase_command.py` (contract, stdlib-only, help, parity across both progs for bare/help/version/flags/config/lint/offline tone render/BrokenPipeError, completion marks), buildinfo both-modes, feedhost both-forms/127/tightened-detection. Full `sase tool run check` green: 381 passed, 4 skipped, ruff + mypy-strict + codespell clean; `mkdocs build --strict` passes; `epic-symbols` empty.

No memory edits (records land in acceptance). Final declaration accepted for the commit finalizer with `bead_action: keep`, since the bead was already closed with `sase bead close`.
