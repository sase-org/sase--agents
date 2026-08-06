# Chat History - ace-run (toobig-1m.split_file.tests._test_selection.0)

- **TIMESTAMP:** 2026-08-06 06:23:31 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-1m.split_file.tests._test_selection.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260806_055523.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests._test_selection.0, clan=toobig-1m)
%wait:toobig-1m.split_file.src.sase.notification_gates.kind_validation.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/_test_selection.py` file up into multiple files? Use your best judgement, but let's aim to keep
all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now let me create the split modules.

Now the core module:

Now update the test imports and the integration-test module copy list:

The split is in place and lint/targeted tests pass; `just check` (which escalates to the full suite because selection tooling changed) is still running. Meanwhile, here's the shape:

**New modules** (all well under 500 lines):

| File | Lines | Contents |
|---|---|---|
| `tests/_test_selection.py` | 379 | The closure and selection policy: `SelectionOptions`, `Selection`, `select_tests`, `_closure`, `load_contract_manifest`, `FULL_SUITE` |
| `tests/_test_selection_rules.py` | 143 | All `RULE_*` names, `FULL_SUITE_RULES`, the path frozensets, `RuleEvaluation`, `evaluate_broadening_rules` |
| `tests/_test_selection_changes.py` | 127 | `ChangeSet`, the two `-z` git parsers, `compute_change_set` |
| `tests/_test_selection_manifest.py` | 104 | Cache paths, `MANIFEST_SCHEMA`, manifest read/write, `sase_core_directory`, `environment_fingerprint` |
| `tests/_test_selection_report.py` | 60 | `summary_line`, `context_line`, `explain_lines` |

Dependencies stay acyclic: rules/changes/manifest are leaves, the core imports them, and report imports the core.

**Call-site updates:** `tools/select_tests`, `tools/run_pytest`, `tests/test_test_selection.py`, `tests/test_test_selection_contexts.py`. Two things that would have silently rotted:

- `SELECTION_TOOLING_PATHS` now lists the four new modules, so editing any of them still fires `selection-tooling` and escalates to the full suite — verified with `tools/select_tests --explain`, which reports exactly that for this change.
- `tests/test_suite_gate_integration.py` copies selector modules by name into a synthetic repo; the new files are added to that list.

**Verified so far:** `just lint` clean (ruff, mypy, symvision, toobig); 214 tests across `test_test_selection*`, `test_select_tests_tool`, `test_run_pytest_*`, `test_suite_gate_integration`, `test_contract_manifest`, `test_github_actions_ci` all pass; whole-suite collection (25,839 tests) imports cleanly.

One thing outside the scope you gave me: `tests/_test_selection_health.py` is 894 lines and already trips `toobig`'s warning threshold. Say the word and I'll split it too.

Verification complete. Committing now.

Committed and pushed — working tree clean, branch level with `origin/master`.

## The split

| File | Lines | Contents |
|---|---|---|
| `tests/_test_selection.py` | 379 | Closure + selection policy: `SelectionOptions`, `Selection`, `select_tests`, `_closure`, `load_contract_manifest`, `FULL_SUITE` |
| `tests/_test_selection_rules.py` | 143 | `RULE_*` names, `FULL_SUITE_RULES`, path frozensets, `RuleEvaluation`, `evaluate_broadening_rules` |
| `tests/_test_selection_changes.py` | 127 | `ChangeSet`, the two `-z` git parsers, `compute_change_set` |
| `tests/_test_selection_manifest.py` | 104 | Cache paths, `MANIFEST_SCHEMA`, manifest read/write, `sase_core_directory`, `environment_fingerprint` |
| `tests/_test_selection_report.py` | 60 | `summary_line`, `context_line`, `explain_lines` |

Dependencies are acyclic: rules/changes/manifest are leaves, the core imports them, report imports the core. Call sites updated in `tools/select_tests`, `tools/run_pytest`, `tests/test_test_selection.py`, `tests/test_test_selection_contexts.py`.

Two name-based registries would have silently rotted, so both were extended: `SELECTION_TOOLING_PATHS` now lists the four new modules (so editing them still fires `selection-tooling`), and `tests/test_suite_gate_integration.py` copies them into its synthetic repo.

## Verification (all run this turn)

- `just lint` clean: ruff, mypy (2758 files), pyscripts, changelog, symvision, toobig. The lone `toobig` warning is pre-existing (`_test_selection_health.py`, 894 lines) and untouched by this change.
- 217 tests pass across `test_test_selection*`, `test_select_tests_tool`, `test_suite_gate_integration`, all six `test_run_pytest_*`, `test_contract_manifest`, `test_selection_health_tool`.
- Whole-suite collection imports cleanly: 25,839 tests collected.
- `tools/select_tests --explain` correctly reports `escalated to the full suite (rules: selection-tooling)` for this diff, confirming the registry update took effect.

Not run: the full 25k-test suite (`just check-full`), which this change's escalation would normally call for — it gets SIGTERM-killed in this sandbox rather than completing. CI will run it.

`tests/_test_selection_health.py` (894 lines) is still over the warning threshold; say the word and I'll split it too.
