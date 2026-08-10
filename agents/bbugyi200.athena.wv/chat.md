# Chat History - ace-run (wv)

- **TIMESTAMP:** 2026-08-10 08:18:20 EDT
- **MODEL:** claude/opus
- **AGENT:** wv

## Prompt

#gh:gh_sase-org__sase What file do I need to modify to change the default values of builtin model aliases? Do I have to change any other files or is a single file change sufficient? %model:opus

## Response

I'll look into how builtin model aliases are defined.

## The file

**`src/sase/llm_provider/model_alias_defaults.yml`**

That's the single edit point, and it's designed that way deliberately. Each of the 14 builtin aliases gets at most one of `target` (concrete model / `A | B` pool / `A || B` ordered fallback) or `fallback` (`@alias`, optionally `@effort`), plus a required `description`. `src/sase/llm_provider/model_alias_policy.py:4` states it outright: editing that YAML is the only change needed to alter what an implicit alias resolves to. The policy module owns only the alias *name* constants and the cached loader (`implicit_alias_targets()`, `role_alias_fallbacks()`, `role_alias_descriptions()`).

## Is one file enough?

For a pure **value** change (e.g. pointing `@smartest` at a different model), yes — with one mechanical follow-up:

- **Run `just fmt-docs`** (also covered by `just fmt` / `just fix`). `docs/llms.md:986` has a generated `model-alias-defaults` table rendered from the YAML by `tools/render_model_alias_docs`. Nothing lints for staleness — `fmt-check` only covers Python and Markdown formatting — so if you skip it the docs silently drift.

Things you do **not** need to touch:

- **Tests.** `tests/conftest.py:463` installs an autouse fixture that swaps in frozen fake defaults, so tests don't observe shipped values. Hardcoded strings like `"claude/sonnet@xhigh | codex/gpt-5.5"` in `tests/test_config_schema_models.py:73` are user-config *fixtures* exercising the grammar, not assertions about shipped defaults.
- **`src/sase/default_config.yml:840-861`.** Those commented alias examples are explicitly labeled grammar examples, not shipped defaults.
- **`CHANGELOG.md`.** Release-please generates it; `_lint-changelog` rejects hand-written sections.

## The one case that needs a second file

If you change the alias **graph shape** rather than a value — an alias switches between `target` / `fallback` / neither, or a `fallback` retargets to a different alias — you must also update `tests/_model_alias_defaults_fixture.py`. That map deliberately freezes the graph as a contract while keeping its concrete values distinct from the shipped ones, so value coupling stays visible. Its module docstring spells out the rule.

Since this repo treats shared backend behavior as belonging in `../sase-core`, note the alias defaults currently live on the Python side — nothing in the Rust core needs touching for this.
