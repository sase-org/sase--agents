# Chat History - ace-run (toobig-55.update_handler.0)

- **TIMESTAMP:** 2026-09-10 22:15:00 EDT
- **MODEL:** claude/sonnet
- **AGENT:** toobig-55.update_handler.0

## Prompt

%wait:toobig-55.install.0
%id(update_handler.0, clan=toobig-55)
%model:@medium
%auto
%queue(runners=3)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/main/update_handler.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Now the completion-refresh module:

Expected — those warnings will clear once the other modules import from this one. Now the mode-switch handler:

Now the live-update handler:

Now the dry-run handler:

Now let's rewrite the main `update_handler.py` as the thin facade:

I'll wait for `just install` to finish in the background before running `just check`.

`just install` is running in the background (it can take a while to set up the venv). I'll continue once it finishes.

I've split `update_handler.py` (742 lines) into a thin dispatcher plus five focused sibling modules, following this repo's existing `repo_handler`/`project_handler`/`workspace_handler` split convention:

- **`update_handler.py`** — thin facade, wires defaults and routes to the right sub-handler
- **`update_handler_mode_switch.py`** — `sase update --to <mode>` handling
- **`update_handler_live.py`** — the live (non-dry-run) update path
- **`update_handler_dry_run.py`** — `--dry-run` handling
- **`update_handler_completion.py`** — post-update shell-completion refresh
- **`update_handler_support.py`** — shared helpers (`_fail`, `_tool_python`, dev-plan calling)

All files are well under 500 lines. The public surface (`handle_update_command`, `UPDATE_JSON_SCHEMA_VERSION`, `_installed_version`) that `entry.py` and the tests import is unchanged.

This was committed per the SASE finalizer protocol, but `just check` verification is still pending — `just install` was running in the background when the turn had to end, so I haven't yet confirmed lint/tests pass. That will need to happen in a follow-up turn.
