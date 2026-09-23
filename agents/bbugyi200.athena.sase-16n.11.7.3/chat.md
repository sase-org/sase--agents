# Chat History - ace-run (sase-16n.11.7.3)

- **TIMESTAMP:** 2026-09-23 15:02:44 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16n.11.7.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-16n.11.7, bead=sase-16n.11.7.3)
%model:@medium
%auto
%w:sase-16n.11.7.1
%w(bead=sase-16n.11.7.1)
Can you complete the work for bead sase-16n.11.7.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16n.11.7.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16n.11.7.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16n.11.7.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16n.11.7.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16n.11.7.3 is complete and closed.

What was done (all phase scope items):
- Pin ratcheted to sase-core `fb1ca29` (core-accept HEAD).
- `frozen_intent_vcs_prefix`: only a resolved `+tag` token counts as prefixed, matched via the tag scanner (new `tests/monitor/test_followup_intent_prefix.py`; verified the prose case fails on old code).
- Prompt-history filter is peek-only: new `expand_project_tags_with_catalog` helper, `_segment_active_ref` never builds, falls back to raw text when cold; three new modal-path tests including a never-builds assertion.
- `tests/conftest.py` autouse fixture clears the tag catalog cache after each test (visual suite's monkeypatch pin unaffected).
- Missing assertions: completion `current` badge + MRU order now asserted from the real store; cold-cache tagify end-to-end for `prompt show`, `agent show`, and `prompt list`; alt fan-out with literal `%{+sase | +bob-cli}`; `+tag` prefix substitution for the MRU entry path.
- Small fixes: raw/JSON `prompt show` skips catalog warm (pinned by test); `occupant_kind` in doctor collision JSON (pinned by test).
- Docs nits in `docs/editor.md`, `docs/getting_started.md`, and the `resolve_xprompt_aliases` docstring.

Verification: 236 + 232 focused tests pass; `ruff`, `mypy`, `fmt` clean. `just check` fails only on a pre-existing symvision error (stale `--epic-symbol sase-16y(MemberJumpSection)`, fails identically on the clean tree) — recorded as a `PROPOSED FOLLOW-UP` note on the bead for the land agent.
