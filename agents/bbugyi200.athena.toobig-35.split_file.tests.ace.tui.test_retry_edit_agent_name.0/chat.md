# Chat History - ace-run (toobig-35.split_file.tests.ace.tui.test_retry_edit_agent_name.0)

- **TIMESTAMP:** 2026-08-19 01:28:46 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-35.split_file.tests.ace.tui.test_retry_edit_agent_name.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_225904.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.ace.tui.test_retry_edit_agent_name.0, clan=toobig-35)
%wait:toobig-35.split_file.tests.ace.tui.test_agent_panel_titles.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/ace/tui/test_retry_edit_agent_name.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

Clear seam here, and it mirrors an existing convention: the kill-and-edit side is already split into `test_kill_and_edit_prompt_name.py` (pure rewriting contract) and `test_kill_and_edit_agent_name.py` (app action). I'll split retry the same way.

Now let me verify: install, run the tests, and lint.

All gates pass. Split done:

| File | Lines | Covers |
|---|---|---|
| `tests/ace/tui/test_retry_edit_prompt_name.py` | 137 | Pure `rewrite_retry_prompt_name` / `_rewrite_retry_prompt_name` contract — prepend/replace of `%id` and `%i`, bare `%id` not allocating, template names, tribe/family/clan keyword preservation, fenced-and-disabled directive skipping, and the `directive_alias="i"` variants |
| `tests/ace/tui/test_retry_edit_agent_name.py` | 194 | The `_App._retry_edit_agent()` action — retry-name allocation, qualified-local name handling, unnamed-agent passthrough, clan demotion/joiner preservation |

The seam mirrors the existing kill-and-edit pair (`test_kill_and_edit_prompt_name.py` / `test_kill_and_edit_agent_name.py`), so the four files now line up as prompt-contract vs. app-action for both retry and kill. Imports are narrowed per file (`Mock` only in the action module, the rewrite functions only in the contract module); the autouse `_configured_machine_identity` fixture is imported in both, as the kill-and-edit pair does. No test bodies changed — all 23 tests preserved and passing, plus the 41 kill-and-edit tests that share the helpers module.

One note: the original file was 324 lines, already under your 500-line target — so this was a readability split rather than a size fix. Both halves are well clear of the limit either way.

These are my changes from this session. Let me re-verify quickly, then commit.

All 23 tests pass. Committing now.

Committed and pushed — working tree clean, branch level with `origin/master`.

**Commit `b997ba264`** — `test(tui): split retry edit tests into prompt and agent modules`

| File | Lines | Covers |
|---|---|---|
| `tests/ace/tui/test_retry_edit_prompt_name.py` | 137 | Pure `rewrite_retry_prompt_name` / `_rewrite_retry_prompt_name` contract — prepend/replace of `%id` and `%i`, bare `%id` not allocating, template names, tribe/family/clan keyword preservation, fenced-and-disabled directive skipping, and the `directive_alias="i"` variants |
| `tests/ace/tui/test_retry_edit_agent_name.py` | 194 | The `_App._retry_edit_agent()` action — retry-name allocation, qualified-local names, unnamed-agent passthrough, clan demotion/joiner preservation |

The seam mirrors the existing kill-and-edit pair (`test_kill_and_edit_prompt_name.py` / `test_kill_and_edit_agent_name.py`), so retry and kill now line up the same way: prompt-contract vs. app-action. No test bodies changed; all 23 tests pass (re-verified in this turn).

One caveat on the outcome: the commit's before-hook (`just fix`) and the provider dispatch both succeeded, but `sase_git_commit` warned that the project has 15 quarantined agent-hood publication requests, so the agent link written into this commit may not resolve until someone runs `sase agent sync --retry-quarantined`. That's a pre-existing outbox backlog, not something this commit introduced.

Also worth restating: the original file was 324 lines, already under your 500-line target — this was a readability split rather than a size fix.
