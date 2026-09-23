# Chat History - ace-run (sase-171.1)

- **TIMESTAMP:** 2026-09-23 13:26:45 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-171.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-171.1, bead=sase-171.1)
%clan(sase-171, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-171.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-171.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-171.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-171.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-171.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Verification is running; I will report once it completes.

Scoped tests still running; I will continue once their result arrives.

Bead sase-171.1 is done and closed.

What landed: the shared installer now handles npm-packaged CLIs. Added `InstallRoute` ([models.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/agent_clis/models.py)) and a pure `describe_agent_cli_install` classifier ([install.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_29/src/sase/agent_clis/install.py)); the planner dispatches on route with a new npm branch (npm/PATH/writability checks via the public `probe_npm_global_environment` helper, `argv=("npm", "install", "-g", package)`, plan-time PATH status, no sudo), plus a per-entry `progress_fn` hook. CLI rendering, dry-run JSON (`method`, `install_dir_on_path`), prompt, help text, package exports, hookspec docstring, and the `agent_providers` / `cli` / `getting_started` / `plugins` docs are updated.

Verified: 92 agent_clis tests pass; live `install qwen -n -f` previews the npm command with target and PATH status, `agy` stays a manual skip, Muse output unchanged; all lint gates pass except a symvision hit and 15 test_bead failures that I confirmed fail identically on the pristine tree (recorded as a `PROPOSED FOLLOW-UP` on the bead for the land agent). No epic-symbol entries remained.
