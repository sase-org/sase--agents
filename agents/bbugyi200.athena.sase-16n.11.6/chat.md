# Chat History - ace-run (sase-16n.11.6)

- **TIMESTAMP:** 2026-09-23 12:00:22 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16n.11.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-16n.11, bead=sase-16n.11.6)
%model:@small
%auto
%w:sase-16n.11.1,sase-16n.11.2,sase-16n.11.3,sase-16n.11.5
%w(bead=sase-16n.11.1)
%w(bead=sase-16n.11.2)
%w(bead=sase-16n.11.3)
%w(bead=sase-16n.11.5)
Can you complete the work for bead sase-16n.11.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16n.11.6 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16n.11.6 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16n.11.6`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16n.11.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16n.11.6 (project tag docs accuracy pass) is done and closed.

What changed:
- [docs/editor.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/sase/docs/editor.md): semantic-token legend now includes `saseProjectTag` with `sigil`/`unknown`/`disabled`/`accent0`–`accent17` (verified against `semantic_tokens.rs`; the sigil token also carries the name's resolution modifier), fixed the "every token uses a standard type" sentence, mentioned tags in the Semantic highlighting row, and documented `experimental.sase.projectTagPalette` plus the `disabled_project_tag` diagnostic (codes verified in `project_tags.rs`).
- [docs/xprompt.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/sase/docs/xprompt.md): `#gh:sase #!sync` example now uses `+sase`; `gh_sase` alias example replaced with non-project `deploy_notes`.
- [docs/configuration.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/sase/docs/configuration.md) and `src/sase/config/sase.schema.json`: same alias-example replacement (schema is hand-maintained, the source of that text).
- `src/sase/main/parser_prompt.py`: `-P` help now uses `#`-ref examples and states unexpanded `+tag`s are left alone, matching the limitation in `docs/prompt.md`. No help-text test asserts the old wording, so none needed updating.
- [docs/getting_started.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/sase/docs/getting_started.md): `+<name>` is now presented as the way to target an existing project; `#git:<name>` stays for creating one.
- sase-github `docs/xprompts.md`: the `#gh(sase)` note now says plain targeting uses `+sase` and the paren form is for arguments.

Verification: fresh-machine `+home` check passed 7/7 example prompts against `validate_project_tags_for_launch` on an empty `SASE_HOME`; `sase tool run check` passed; prompt parser/replay (23) and alias (28) tests pass; `epic-symbols` clean; bead closed.

One finding for the land agent: sase-github's wrapped `check` could not run — its recipe fails at `install` with unsatisfiable pins (`sase>=0.17.0` needs `sase-core-rs<0.33.0`, only `>=0.34.23` available). Pre-existing environment issue, unrelated to the 2-line docs edit; its tree contains only that edit.
