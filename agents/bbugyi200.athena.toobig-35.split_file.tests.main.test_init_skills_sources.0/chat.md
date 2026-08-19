# Chat History - ace-run (toobig-35.split_file.tests.main.test_init_skills_sources.0)

- **TIMESTAMP:** 2026-08-19 02:00:35 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-35.split_file.tests.main.test_init_skills_sources.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_225904.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.main.test_init_skills_sources.0, clan=toobig-35)
%wait:toobig-35.split_file.tests.ace.tui.visual.test_ace_png_snapshots_custom_gate.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/main/test_init_skills_sources.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I'll build the split. First, add the shared whitespace helper to the existing helpers module:

Now I'll extract the four modules from the original file:

All four modules are under 500 lines. Now let me verify they run and pass lint:

All 32 tests pass (same count as before the split). Now the repo gates:

Done. `just check` is green (the scoped lane escalated to the full suite and passed).

## The split

`tests/main/test_init_skills_sources.py` (703 lines) → four modules, split along what each group actually exercises:

| File | Lines | Contents |
|---|---|---|
| `test_init_skills_sources.py` | 324 | The 17-case parametrized `test_shipped_skill_source_is_discoverable_for_all_skill_providers` — keeps the original name since it's the module's core "source discovery" subject |
| `test_init_skills_provider_targets.py` | 171 | Provider-scoped generation: agy/grok native targets, the config-defined-skill migration diagnostic, `--provider` filtering |
| `test_init_skills_source_content.py` | 125 | Pure content assertions against shipped `.md` sources (gate v2 contract, plan model aliases, repo web-fetch description, commit-skill legacy flags, `sase_new_task` scoping, git-commit wrapper) — no generation, no `tmp_path` |
| `test_init_skills_source_integrity.py` | 115 | The three `_init_skills_source_integrity` git checks (clean/dirty/unlanded), which only touch `source_integrity` and never the handler |

## Shared code

`_collapse_whitespace` was needed by two of the modules, so it moved to the existing `tests/main/init_skills_handler_helpers.py` as public `collapse_whitespace` alongside `make_args`. The autouse prettier-disabling fixture stayed file-local in the two modules that actually generate files; the content and integrity modules don't render anything, so they don't need it.

No test bodies changed, and imports are narrowed per module (`re`/`subprocess`/`XPrompt` each now live only where used). 32 tests before, 32 after.

32 tests pass. Committing now.

Committed as `d7d059d9a`; working tree is clean and `master` is level with `origin/master`.

## What landed

`tests/main/test_init_skills_sources.py` (703 lines) → four modules, all under 500 lines:

| File | Lines | Contents |
|---|---|---|
| `test_init_skills_sources.py` | 324 | The 17-case parametrized `test_shipped_skill_source_is_discoverable_for_all_skill_providers` — keeps the original name since source discovery is the module's core subject |
| `test_init_skills_provider_targets.py` | 171 | Provider-scoped generation: agy/grok native targets, the config-defined-skill migration diagnostic, `--provider` filtering |
| `test_init_skills_source_content.py` | 125 | Pure content assertions against shipped `.md` sources — no generation, no `tmp_path` |
| `test_init_skills_source_integrity.py` | 115 | The three `_init_skills_source_integrity` git checks (clean/dirty/unlanded) |

`_collapse_whitespace` was needed by two modules, so it moved to the existing `tests/main/init_skills_handler_helpers.py` as public `collapse_whitespace`. No test bodies changed.

## Verification

Re-ran the four modules in this turn: **32 passed**, same count as before the split. `just check` was green in the earlier pass (its scoped lane escalated to the full suite and passed); the pre-commit `just fix` hook also ran clean during the commit. I did not re-run the full `just check` in this turn — the only thing between that green run and the commit was the commit itself.

One warning from the commit, unrelated to these changes: the project has 15 quarantined agent-hood publication requests, so the agent link attached to this commit may not resolve until `sase agent sync --retry-quarantined` clears the outbox.
