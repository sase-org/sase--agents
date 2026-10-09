# Chat History - ace-run (sase-1if.6)

- **TIMESTAMP:** 2026-10-09 05:37:49 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1if.6

## Prompt

%auto
#gh:gh_sase-org__sase
%id(6, clan=sase-1if, bead=sase-1if.6)
%model:@small
%w(sase-1if.5, for_epic=false)
%w(bead=sase-1if.5)
Can you complete the work for bead sase-1if.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1if.6 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1if.6 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1if.6`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1if.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead sase-1if.6 (pre-install command preview) is complete and closed.

What was built: a new `declared_commands` module that reads an uninstalled plugin's `sase_commands` from its upstream `pyproject.toml` through `gh` (raw media type), parsed with `tomllib`, cached in `plugins/declared_commands_cache.json` keyed by `full_name` with `updated_at`/7-day invalidation. Every failure mode (missing file, dynamic entry-points, no `gh`, fetch failure, offline, parse error) yields `unknown`, which renders nothing. Collisions are flagged with the mount rules: reserved names would be shadowed, installed-owned names would conflict with both disabled. The preview surfaces in `plugin_entry_json` for `show -j`/`list -j`, in the `install -n` dry-run panel ("Adds command ❯ sase listen" plus warnings) and its JSON, and on the TUI `InstallPreview`. Installed plugins always win over the preview. The shared reservation rule is now public (`reserved_command_names`) per symvision's directive.

Verification: 32 new tests plus 191 neighboring tests green; gate stages fmt, ruff, mypy, feature-flags, pyscripts, changelog, and terminology green; symvision reports nothing in touched files; no epic-symbol leftovers. The `lint (test waits)` gate is red on `test_plan_decision_ace_stale.py`, which is untouched by this work, fails identically on other trees, and is already tracked in sase-1if-adjacent beads — recorded as a `PROPOSED FOLLOW-UP` per the phase rules, and it did not block closing.
