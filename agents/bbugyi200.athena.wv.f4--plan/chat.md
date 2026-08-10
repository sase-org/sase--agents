# Chat History - ace-run (wv.f4--plan)

- **TIMESTAMP:** 2026-08-10 12:00:27 EDT
- **MODEL:** claude/opus
- **AGENT:** wv.f4--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-wv_f4__plan-260810_110854.md`
- 2. --code — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-wv_f4__code-260810_110854.md`

**Plan:** /home/bryan/.sase/plans/202608/smarter_model_alias.md


## Prompt

#gh:gh_sase-org__sase 
%xprompts_enabled:false
# Previous Conversation

**User:**

What file do I need to modify to change the default values of builtin model aliases? Do I have to change any other files or is a single file change sufficient?

**Assistant:**

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

---

%xprompts_enabled:true
# New Query

 %w:xc Can you help me make the following changes to these
defaults?:

- Add a new `@smarter` model alias that defaults to
  `codex/gpt-5.6-sol@xhigh | claude/opus@xhigh`.
- `@default` should map to `@smarter`, so the .
- Let's change the default of the existing `@smart` model alias to
  `codex/gpt-5.5@xhigh | claude/sonnet@xhigh`.
- Change the default of the existing `@cheap` model alias to use
  `claude/sonnet@high | codex/gpt-5.5@high`
- The `@medium_worker` model alias should map to `@smart` and the `@large_worker` should
  be changed to map to `@smarter`.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/smarter_model_alias.md`

> # Add `@smarter` and retarget the shipped model alias defaults
> ## Goal
> Reshape SASE's shipped builtin model alias graph:
> | Alias           | Shipped default after this change              | Change kind                                                    |
> | --------------- | ---------------------------------------------- | -------------------------------------------------------------- |
> | `smarter`       | `codex/gpt-5.6-sol@xhigh \| claude/opus@xhigh` | **new alias**                                                  |
> | `default`       | `@smarter`                                     | **new shape** (was: neither target nor fallback)               |
> | `smart`         | `codex/gpt-5.5@xhigh \| claude/sonnet@xhigh`   | **new shape** (was fallback `@default`)                        |
> | `cheap`         | `claude/sonnet@high \| codex/gpt-5.5@high`     | value only (was `claude/sonnet@xhigh \| codex/gpt-5.5@medium`) |
> | `medium_worker` | `@smart`                                       | **new shape** (was target `codex/gpt-5.5@xhigh`)               |

*See full plan file for details.*

