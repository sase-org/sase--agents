# Chat History - ace-run (sase-aq.2)

- **TIMESTAMP:** 2026-07-29 09:46:44 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-aq.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-aq, bead=sase-aq.2)
%model:@small_phase_worker
%auto
%w:sase-aq.1
%w(bead=sase-aq.1)
Can you complete the work for bead sase-aq.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-aq.2 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now let me look at the current state of the code.

The new bindings are live locally. Now let me read the Python facade.

Now the prompt-grammar files and validation:

Now the validation path:

Now let me check the names package exports and existing tests.

Now I have the full picture. Let me make the edits, starting with the facade.

Now the exports:

Now the pyproject bump and the claim-time guard.

Facade works. Now let me verify the grammar plumbing round-trips through the actual extractors.

Now let me write the tests.

Now the grammar round-trip tests:

All new tests pass. Now the full check:

Now fixing the symvision finding — the sibling validation errors in that file are all private, so I'll match that:

The lint stages are all green; the only failure is the version window. Let me confirm the test suite passes and verify the version situation is a genuine blocker.

Confirmed a real regression: `}` in the flat trailing class swallowed the alt-fanout group's closing brace. The fix is to admit the marker as a unit rather than loose braces.

Both patterns now behave. Let me add a regression test for the interaction that broke, then re-verify.

Full suite green (23498 passed) and every lint stage passes. Let me close the bead.

Bead `sase-aq.2` is closed. Summary of the work:

**Facade** (`src/sase/agent/names/_templates.py`): `AgentNameTemplateKey` and `AgentNameKeyMarker` dataclasses, `agent_name_template_key()` / `iter_agent_name_key_markers()` wrappers over the grammar phase's bindings, and `marker`/`key` fields on `AgentNameTemplate`. Also fixed `agent_name_template_base()` to strip the *parsed* marker rather than a hard-coded `@`, which would otherwise mangle `research.{@1}.cdx` into `research.{1}.cdx`. All exported from `sase.agent.names`.

**Prompt grammar**: I deviated from the plan's literal instruction here, for a concrete reason. Adding `{`/`}`/`!` to the flat colon-arg character classes broke `test_launch_multi_prompt_text_alt_model_alt_uses_distinct_generated_templates` — a loose trailing `}` let `%m:#codex}` swallow the closing brace of the enclosing `%{a | b}` fan-out group, producing agent names like `0.1.cld_opus`. Instead both `_DIRECTIVE_PATTERN` and `_XPROMPT_PATTERN` now admit a shared `KEY_MARKER_PATTERN` as an indivisible alternative, so an unmatched `}` still terminates the argument. Regression test added. `_DIRECTIVE_PREFIX_RE` and `parse_args` needed no change, covered by tests as the plan specified.

**Validation**: a claim-time guard in `validate_user_agent_name` that names the surviving marker and says the launch pipeline failed to resolve it.

**Verification**: 25 new tests; full suite green at 23498 passed, and every `just check` lint stage passes.

One thing needs your decision. `just check`'s *SASE validation* stage fails, and not for a reason I can fix in this repo:

- I bumped `pyproject.toml` to `sase-core-rs>=0.12.8,<0.13.0`, but 0.12.8 isn't on PyPI yet. The grammar phase landed on sase-core master as `8facc89`, and release-plz PR #45 (`chore: release v0.12.8`) is still open.
- The bump can't simply be reverted: `parse_agent_name_template` now reads `payload["marker"]`, which the 0.12.7 binding doesn't return — a released install pinned to 0.12.7 would `KeyError` on every template parse.

Merging that sase-core release PR unblocks the gate. I didn't merge it myself since publishing to PyPI/crates.io is irreversible and outward-facing — say the word and I'll do it, or you can merge it directly. Local dev installs build from the `sase-core` checkout, so the facade works today regardless.

Bead is closed. Committing now.

Committed and pushed; working tree clean, branch level with `origin/master`.

**What shipped** (bead `sase-aq.2`, already closed before the commit):

- **Facade** — `AgentNameTemplateKey` / `AgentNameKeyMarker` dataclasses, `agent_name_template_key()` and `iter_agent_name_key_markers()` over the sase-core grammar bindings, plus `marker`/`key` fields on `AgentNameTemplate`, all exported from `sase.agent.names`. Also fixed `agent_name_template_base()` to strip the *parsed* marker rather than a hard-coded `@`.
- **Prompt grammar** — `_DIRECTIVE_PATTERN` and `_XPROMPT_PATTERN` admit a shared `KEY_MARKER_PATTERN` as an indivisible alternative instead of loosening the colon-arg character class. The plan called for the latter, but it let `%m:#codex}` swallow the closing brace of an enclosing `%{a | b}` fan-out group; regression test added.
- **Validation** — claim-time guard in `validate_user_agent_name` naming the unresolved marker.
- 25 new tests; full suite green at 23498 passed, all `just check` lint stages pass.

One item still outstanding, unchanged from before and not something I can resolve in this repo: the committed `pyproject.toml` pins `sase-core-rs>=0.12.8,<0.13.0`, and **0.12.8 is not yet published** — release-plz PR #45 on sase-core is still open. `just check`'s SASE validation stage will fail until it merges. The pin can't be reverted, since `parse_agent_name_template` reads the `marker` payload field that 0.12.7 doesn't return. Local dev installs build from the `sase-core` checkout and work today. Merging that release PR is publishing to PyPI/crates.io, so I left it for you — say the word and I'll do it.
