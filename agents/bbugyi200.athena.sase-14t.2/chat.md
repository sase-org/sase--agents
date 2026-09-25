# Chat History - ace-run (sase-14t.2)

- **TIMESTAMP:** 2026-09-20 22:33:50 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-14t.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-14t, bead=sase-14t.2)
%model:@medium
%auto
%w:sase-14t.1
%w(bead=sase-14t.1)
Can you complete the work for bead sase-14t.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-14t.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14t.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14t.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-14t.2 is done and closed.

Result: `#research_swarm` now runs four provider-gated researchers (codex/claude on by default, grok/muse opt-in) plus an always-run lead. Inputs renamed to `codex`/`claude`/`grok`/`muse` and `<provider>_model` with concrete per-provider defaults, report suffixes are `__cdx`/`__cld`/`__grk`/`__mus`, and the clan declaration moved to the lead. `default_config.yml` drops `sol_or_grok`/`opus_or_grok`, keeps `image`, with a rewritten `researchers` bucket. Docs (README, `docs/xprompts.md`, `docs/configuration.md`, `AGENTS.md`) updated; `pyproject.toml` floor untouched, with notes that provider gating needs a host sase carrying the `provider_enabled`/`provider_disabled` filters.

Verification: `just check` green (ruff + mypy + 58 tests passed), and a `plan_typed_launch_units` dry run showed all units sharing one clan with tribe/summary resolving on the lead declarer, so the Jinja fallback was not needed. `epic-symbols` was clean, the bead was closed with that evidence, and the final declaration was accepted with a `commit` carrying the `BREAKING CHANGE` trailer.

One finding for the land agent, recorded as `PROPOSED FOLLOW-UP` on the bead: `research-highlights` `agent_name_globs` still only excludes `cld`/`cdx` agents, so top-level `__grk`/`__mus` drafts could trigger per-draft Highlights PDFs; `provider.py`'s `__a`/`__b` docstring is also stale.
