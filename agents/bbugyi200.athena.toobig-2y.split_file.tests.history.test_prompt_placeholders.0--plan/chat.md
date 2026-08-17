# Chat History - ace-run (toobig-2y.split_file.tests.history.test_prompt_placeholders.0--plan)

- **TIMESTAMP:** 2026-08-17 14:24:13 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-2y.split_file.tests.history.test_prompt_placeholders.0--plan
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260817_101206.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.history.test_prompt_placeholders.0, clan=toobig-2y)
%wait:toobig-2y.split_file.tests.ace.tui.models.test_agent_tree.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/history/test_prompt_placeholders.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

# Monitor handoff

This agent delegated the remaining work to a monitor shell.
Monitor ID: htj6z4hsn1y2
Inspect with: sase monitor show htj6z4hsn1y2
Monitor shell: toobig-2y.split_file.tests.history.test_prompt_placeholders.0--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18

Command:

```sh
just check
```

Reason:

Verify the tests/history/test_prompt_placeholders.py split (4 test modules + shared helper module) passes all lint gates and the scoped test lane

Next action:

The user asked to split tests/history/test_prompt_placeholders.py (was 742 lines) into files under 500 lines each. That work is DONE and needs no further edits unless just check reported a failure. The split produced: tests/history/_prompt_placeholders_helpers.py (74 lines, shared fixtures/builders following the existing tests/history/_chat_catalog_provenance_helpers.py convention), tests/history/test_prompt_placeholders.py (191 lines, recording/ordering/limits + prompt-history integration), tests/history/test_prompt_placeholders_store.py (204 lines, durability/corrupt payloads/write failures/source token/removal), tests/history/test_prompt_placeholders_seed.py (196 lines, history seeding + version-1 migration), tests/history/test_prompt_placeholders_context.py (191 lines, context bags/token selection/trimming). All 33 original test functions were preserved verbatim with no behavior changes; a direct pytest run of the four files showed 37 passed. Note the shared sase_home_dir fixture is NOT imported across modules (ruff F811 rejects that); instead each test module defines a thin sase_home_dir fixture delegating to make_sase_home() in the helper module. If just check passed, simply report the split to the user with the file list and line counts. If it failed, fix only what it reported, re-verify, then report.

