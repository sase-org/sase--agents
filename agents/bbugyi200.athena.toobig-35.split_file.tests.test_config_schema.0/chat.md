# Chat History - ace-run (toobig-35.split_file.tests.test_config_schema.0)

- **TIMESTAMP:** 2026-08-19 02:22:21 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-35.split_file.tests.test_config_schema.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_225904.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.test_config_schema.0, clan=toobig-35)
%wait:toobig-35.split_file.tests.test_axe_run_agent_exec_retry.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_config_schema.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

`tests/test_config_schema.py` has already been split — commit `2633d3c2b` ("test(config): split test_config_schema.py by schema domain") did exactly this. The current state:

| File | Lines |
|---|---|
| `tests/test_config_schema.py` | 95 |
| `tests/test_config_schema_automation.py` | 363 |
| `tests/test_config_schema_models.py` | 340 |
| `tests/test_config_schema_repositories.py` | 277 |
| `tests/test_config_schema_agent_experience.py` | 224 |
| `tests/test_config_schema_ace.py` | 183 |
| `tests/test_config_schema_runtime_limits.py` | 164 |
| `tests/test_config_schema_extensions.py` | 155 |
| `tests/test_config_schema_beads.py` | 103 |
| `tests/test_config_schema_keymaps.py` | 99 |
| `tests/test_config_schema_notification_tabs.py` | 78 |
| `tests/test_config_schema_tribes.py` | 81 |
| `tests/test_config_schema_validity.py` | 72 |
| `tests/_config_schema_helpers.py` (shared) | 22 |

Every file is already well under 500 lines, and the remaining `test_config_schema.py` holds the five cross-cutting tests that don't belong to any single domain (schema path resolution, `default_config.yml` conformance, base config without identity, owner/legacy `machine_name`, project glossary shape).

Nothing to do here — no changes made. If you were expecting something different, a couple of possibilities:

- **You meant a different file.** Want me to check for other oversized test files? A quick scan for anything over 500 lines in `tests/` would find them.
- **You want the remaining 95 lines split further** (e.g. glossary → `test_config_schema_glossary.py`, identity → `test_config_schema_identity.py`). Doable, but at 95 lines it'd fragment cohesive coverage without a size justification.

Let me know which.
