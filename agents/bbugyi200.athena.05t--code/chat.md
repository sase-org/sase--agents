# Chat History - ace-run (05t--code)

- **TIMESTAMP:** 2026-08-18 08:16:40 EDT
- **MODEL:** claude/opus
- **AGENT:** 05t--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @sase/repos/plans/202608/agent_restart_command.md

The above plan has been reviewed and approved. Implement it now.


## Response

# Monitor handoff

This agent delegated the remaining work to a monitor shell.
Monitor ID: 9pj0jpyknz8y
Inspect with: sase monitor show 9pj0jpyknz8y
Monitor shell: 05t--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18

Command:

```sh
just check-full
```

Reason:

just check scoped lane escalated (core-identity-changed) after adding sase agent restart; full verification required

Next action:

The previous agent implemented the approved plan at sase/repos/plans/202608/agent_restart_command.md: `sase agent restart NAME`.

Work already done (do not redo unless check-full shows it is broken):
- Moved relaunch prompt helpers to src/sase/agent/relaunch_prompt.py; ACE _entry_name_prompts.py is a thin re-export.
- Added set_prompt_model in src/sase/xprompt/_directive_edit_model.py and exported it.
- Added dismiss_named_agent() in src/sase/agent/running.py.
- Added plan_agent_restart / execute_agent_restart in src/sase/agent/restart.py.
- Added CLI parser/handler/renderer/completion/docs.
- Renamed _ForceReuseLaunchPlan to ForceReuseLaunchPlan so restart.py can import it (symvision private-import rule).
- Regenerated tests/completion/snapshots/cli_spec.json via just sync-completion-spec.
- Tests: tests/test_agent_restart_plan.py, test_agent_restart_execute.py, test_agent_restart_cli.py, plus fixture/parser/kinds/dismiss/directive_edit updates.

just check already passed fmt, ruff, mypy, and other lint gates. Two failures are PREEXISTING on master and already have beads — do not "fix" them as part of this work:
- sase-pm: lint (symvision) unused public long_memory_entry_path and normalize_long_memory_description_lines in src/sase/amd/_agents_doc.py (corroborated +1).
- sase-pn: tests/main/test_init_memory_glossary.py::test_memory_plan_renders_glossary_terms_block_in_tier2 (corroborated +1).

Your job:
1. Read the monitor result. If just check-full failed, distinguish new failures caused by this restart work from sase-pm / sase-pn.
2. Fix only failures caused by this work. Re-run the relevant tests.
3. Reply to the user with a standalone summary of the implemented `sase agent restart` command: surface, flags, exit codes, files, tests, and verification outcome. Do not mention ephemeral workspace directory names.

