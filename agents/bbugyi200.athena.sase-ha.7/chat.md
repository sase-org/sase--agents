# Chat History - ace-run (sase-ha.7)

- **TIMESTAMP:** 2026-08-07 22:31:34 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ha.7

## Prompt

#gh:gh_sase-org__sase
%id(7, clan=sase-ha, bead=sase-ha.7)
%model:@medium_phase_worker
%auto
%w:sase-ha.3,sase-ha.4,sase-ha.5,sase-ha.6
%w(bead=sase-ha.3)
%w(bead=sase-ha.4)
%w(bead=sase-ha.5)
%w(bead=sase-ha.6)
Can you complete the work for bead sase-ha.7? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-ha.7 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ha.7 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

Now I'll make the changes. First a small metadata fix so the install preview can report Muse's target directory:

Now the main `docs/llms.md` sweep:

Now the Muse section in `docs/llms.md`:

Now `docs/agent_providers.md`:

The metadata fix works. Now `docs/configuration.md`:

Now `docs/ace.md`, `docs/plugins.md`, `docs/xprompt.md`, `docs/cli.md`, and `default_config.yml`:

All lint gates pass. The 6 test failures are pre-existing on clean HEAD (from the `notification-gates` commit) and unrelated to this phase — I confirmed by stashing. Recording that and closing:

Done. Bead `sase-ha.7` is closed.

## What changed

**`docs/llms.md`** — the centerpiece. A new **Muse Code Integration** section covering explicit-only selection (and why autodetect is omitted), the exact invocation with the reasoning for each flag, the sandbox default plus the `SASE_MUSE_SANDBOX=on` opt-in and its in-run-commit cost, the model catalog with pricing and the Contributor caveat, the full effort map including `max → ultra`, the five parser rules, tool-call capture with the "tool arguments are never in the stream" limitation stated plainly, session-log usage recovery and recorded model identity, interrupts, skills/`AGENTS.md`, env vars, and timer. Plus a new provider-neutral **Model Advisories** section. Then every enumeration site: intro, TOC, source layout, entry points, autodetect priorities, config example and fields table, `%model` syntax, auto-resolution table, short-alias table, effort matrix, env-var reference, token-usage tracking, streaming mechanism.

**`docs/agent_providers.md`** — a Muse Code install/auth/update section, and the previously undocumented `sase agent-cli install` semantics: HTTPS fetch, digest display, no shell, `--yes`/`--dry-run`/`--force`, PATH reporting, and that SASE never edits shell rc files.

**`docs/plugins.md`** — a new subsection documenting every `llm_install_metadata` key and the `llm_model_advisories` hook, both framed as optional so third-party providers stay compatible.

**Also** `docs/configuration.md` (6 sites + the `install` subcommand row), `docs/ace.md` (badge, tool-call runtimes, picker advisory), `docs/xprompt.md`, `docs/cli.md`, `docs/getting_started.md`, `docs/commit_workflows.md`, and `src/sase/default_config.yml` comments.

## One code change

`muse.py` was missing `install_dir` / `install_dir_env`, so `sase agent-cli install muse --dry-run` printed no target directory — the docs would have described behavior that didn't happen. Two metadata lines fixed it; verified the `target:` line now renders.

## Verification

`just fmt` clean, `just docs-check` builds with no broken anchors (caught and fixed one bad `#plan-approval` link), and all `just check` lint gates pass. Six tests fail — `tests/test_gate_cli_show.py` (4) and `gate_conformance[cli|ace-legacy_shared_input]` — but they fail identically on a stashed clean HEAD, so they came from `e1da6d1b7 feat(notification-gates)`, not this phase. Recorded as a `PROPOSED FOLLOW-UP:` note on the bead rather than swept under the rug.

Changes are uncommitted in the workspace.

Bead is already closed with resolution `done`. Committing now.

Committed and pushed; working tree is clean and `master` is level with `origin/master`.

**Bead `sase-ha.7`** was already closed (resolution `done`, 2026-08-08T02:29:12Z) — the commit run reconfirmed it as `Already closed`.

**Commit** — `docs(llms): document the Muse Code provider end to end`, 11 files, +515/−101:

- **`docs/llms.md`** — new Muse Code Integration section (explicit-only selection, invocation flags, sandbox default plus `SASE_MUSE_SANDBOX=on`, model catalog and pricing, effort map, stream-parser rules, tool-call capture and its limitation, session-log usage recovery, recorded model identity, interrupts, skills, env vars, timer), a provider-neutral Model Advisories section, and Muse added at every existing enumeration point.
- **`docs/agent_providers.md`** — Muse install/auth/update, plus the previously undocumented `sase agent-cli install` semantics.
- **`docs/plugins.md`** — the optional `llm_install_metadata` keys and `llm_model_advisories` hook.
- **`docs/{configuration,ace,xprompt,cli,getting_started,commit_workflows}.md`** and **`default_config.yml`** — provider tables, alias tables, effort matrices, env-var references, config comments.
- **`src/sase/llm_provider/muse.py`** — added `install_dir`/`install_dir_env` so `sase agent-cli install muse --dry-run` actually prints a target directory, matching what the docs now describe.

The `just fix` pre-commit hook ran clean. Lint gates and `just docs-check` passed earlier in the session; six test failures in `tests/test_gate_cli_show.py` and `gate_conformance[cli|ace-legacy_shared_input]` reproduce identically on a stashed clean HEAD, so they predate this work — recorded as a `PROPOSED FOLLOW-UP:` note on the bead for the epic's land agent.
