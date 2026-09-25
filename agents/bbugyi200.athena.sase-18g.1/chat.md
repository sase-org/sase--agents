# Chat History - ace-run (sase-18g.1)

- **TIMESTAMP:** 2026-09-24 19:39:33 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-18g.1

## Prompt

%id(1, clan=sase-18g, bead=sase-18g.1)
#gh:gh_sase-org__sase
%model:@medium
%auto
Can you complete the work for bead sase-18g.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-18g.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-18g.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-18g.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-18g.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open.

## Response

Reading the project memory notes and existing body-text code, then I'll write the module.

Now the same files against the clean base tree.

Bead is closed. Submitting the finalizer declaration.

Phase sase-18g.1 is done and the bead is closed. `just check` does not pass, but every failure it reports also occurs on the clean base tree.

**What I added**
- **`agent_header_preview.py`**: `fit_xprompt_preview` reflows the xprompt Markdown-style and fits it to a width and row budget behind a `▎ ` quote bar. It ends the last row in `…` after the last whole word that fits and reports `hidden_lines`.
- **Budget helper**: `preview_row_budget` returns the cap of `floor(column_rows × share)` minus 4 chrome rows, with a minimum of 1 row when share is above 0. It gives 7 rows for 32 column rows and 12 for 47.
- **`agent_header_settings.py`**: `AgentHeaderSettings`, `parse_agent_header_settings` and `agent_header_settings_for`. The value is `ace.agent_header.collapsed_max_share` (default 0.35, max 0.6). Bools, non-numbers, negatives, values above 0.6 and NaN fall back to the default.
- **Wiring**: the setting is in `sase.schema.json` and `default_config.yml`, parsed in `_state_init_late.py`, and annotated in `startup.py`. It is inert until the panel phase uses it, and `docs/configuration.md` is left for that phase.
- **Symvision**: I added four `--epic-symbol 'sase-18g(...)'` entries to the `Justfile`, keyed to the parent epic so they outlive this phase. They cover the four symbols with no consumer yet: `fit_xprompt_preview`, `XpromptPreviewFit`, `preview_row_budget` and `agent_header_settings_for`. `sase-18g.3` should remove them.

**Verification**
- The 73 preview tests and 21 settings and schema-parity tests pass. That includes a 100k-line source that fits in about 0.02s with the right `hidden_lines`.
- Format, ruff, keep-sorted, feature-flags, pyscripts, changelog and validate all pass. Mypy, toobig and symvision report nothing in the new files.
- `just check` fails at mypy, test-waits, toobig and symvision, and the scoped test lane has 44 failing tests. These are in files I didn't touch (`command_line/*`, the agent-detail mixins, `decks/panel.py`, and others). I stashed my changes and got the same 44 test failures. Symvision reported 49 findings on the clean base and 53 with my four new symbols before whitelisting.
- I recorded that as a `PROPOSED FOLLOW-UP` note on the bead rather than creating a bead.

The finalizer commit declaration was accepted, with `bead_action: "close"` even though I had already closed the bead by hand.
