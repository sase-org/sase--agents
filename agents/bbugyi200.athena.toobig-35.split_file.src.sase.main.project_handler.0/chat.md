# Chat History - ace-run (toobig-35.split_file.src.sase.main.project_handler.0)

- **TIMESTAMP:** 2026-08-19 00:40:20 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-35.split_file.src.sase.main.project_handler.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_225904.md`

## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.main.project_handler.0, clan=toobig-35)
%wait:toobig-35.split_file.src.sase.ace.tui.modals.statistics_pane.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/main/project_handler.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file and how it's used.

Now I'll create the new modules. Starting with the lifecycle module:

Now the slimmed-down `project_handler.py`:

Now the directory-operation audit key and the flake-baseline node id:

The refactor is verified; one unrelated pre-existing test-isolation failure surfaced. Let me file it properly:

Done. `src/sase/main/project_handler.py` (705 lines) is now five modules, all well under 500 lines:

| File | Lines | Contents |
|---|---|---|
| `project_handler.py` | 150 | Subcommand dispatch table, `handle_project_command`, the `list`/`show`/state handlers, and the public re-export surface (`set_project_state_locked`, `delete_project_locked`, `set_project_aliases_locked`, the three error classes) so existing importers (`projects_pane.py`, `launch_projects.py`, TUI modals) are unchanged |
| `project_handler_lifecycle.py` | 280 | Error classes, alias/path resolution, record queries, `set_project_state_locked`, `delete_project_locked` |
| `project_handler_current.py` | 138 | `current` / `set-current` handlers plus their rendering |
| `project_handler_alias.py` | 123 | `alias {list,add,remove,clear}` handlers |
| `project_handler_render.py` | 106 | Table/detail/JSON rendering for records and aliases |

Notes on the split:
- Helpers that cross a module boundary were made public (symvision forbids importing `_name` across files); anything used only inside its new module stayed private. `just _lint-symvision` passes.
- Three small query wrappers absorbed inline logic so `list_project_records` is called from exactly one module: `list_projects_for_state_filter`, `list_aliased_project_records`, `get_project_record`. That also simplified the test stubs — `lifecycle_stubs` now patches `project_handler_lifecycle` only.
- Test patch targets were repointed (`project_handler_current` for the current/set-current tests), and the directory-operation audit key moved to `project_handler_lifecycle.py:delete_project_locked`.

Verification: ruff, ruff format, mypy, symvision, toobig, and the rest of the lint stages pass; `just test` is green (33,891 passed); the `sase project list/current/show/alias` CLI paths smoke-tested fine.

One thing to flag: `just check` is red, but not from this change. Its diff-scoped lane hits `tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch`, which fails deterministically whenever `tests/test_launch_planned_agent_name.py` (or `test_launch_planned_bead_work.py`) ran earlier in the same process — process-global state leaking between tests. It reproduces on a stashed, clean `master` tree with `pytest tests/test_launch_planned_agent_name.py tests/test_multi_prompt_launcher_xprompt_groups.py`, 3/3. My diff only changed which tests the lane co-schedules. Filed as task `sase-qs` (ready), with a `DISCOVERED ISSUE` note on the in-progress epic `sase-j7`, which owns exactly this leak class.

These are my changes from this session. Committing them now.

Committed and pushed — working tree is clean and `master` is in sync with `origin/master`.

**Commit `6f9e5c7da`** — `refactor(main): split project_handler.py into focused modules`

| File | Lines | Contents |
|---|---|---|
| `project_handler.py` | 150 | Dispatch table, `handle_project_command`, `list`/`show`/state handlers, re-export surface |
| `project_handler_lifecycle.py` | 280 | Error classes, alias/path resolution, record queries, `set_project_state_locked`, `delete_project_locked` |
| `project_handler_current.py` | 138 | `current` / `set-current` |
| `project_handler_alias.py` | 123 | `alias {list,add,remove,clear}` |
| `project_handler_render.py` | 106 | Table/detail/JSON rendering |

The original 705-line file is now five modules, all well under 500 lines. Existing importers (`projects_pane.py`, `launch_projects.py`, TUI modals) are unchanged because `project_handler.py` re-exports the lifecycle helpers and error classes. Test patch targets were repointed and the directory-operation audit key moved to `project_handler_lifecycle.py:delete_project_locked`. The `just fix` pre-commit hook ran clean.

Two things worth noting:

- The commit printed a warning that **agent-hood publication for the `research` hood is queued** (duplicate container global name `bbugyi200.athena.research.h.final`). The primary commit and push succeeded; that publication retries on its own and is unrelated to this change.
- `just check` is red for a pre-existing reason, not this diff: `tests/test_multi_prompt_launcher_xprompt_groups.py::test_launcher_qualifies_research_swarm_per_dispatch` fails deterministically when `tests/test_launch_planned_agent_name.py` runs earlier in the same process. It reproduces on a clean `master` tree. Filed as task `sase-qs` with a note on epic `sase-j7`, which owns that leak class.
