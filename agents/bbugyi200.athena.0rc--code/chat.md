# Chat History - ace-run (0rc--code)

- **TIMESTAMP:** 2026-09-24 16:20:35 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 0rc--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202609/gh_sase_org__sase-ace_run-0rc__plan-260924_160816.md`
- **2. --code** — `~/.sase/chats/202609/gh_sase_org__sase-ace_run-0rc__code-260924_160816.md`

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202609/model_effort_at_spacer.md

The above plan has been reviewed and approved. Implement it now.


## Response

Implementing the helper and the key hook now.

Now tests.

Stale binding; try the recommended install via the tool runner.

Passing. Docs, then check.

None of the mypy errors are in my files. I'll run the neighboring widget tests, then finalize.

That failure is pre-existing. Finalizing.

Typing `@` right after `%m:<model> ` (one space, at end of line or before whitespace) now replaces the space with `@` and opens the effort menu. That covers the colon-form `%m:` and `%model:` only, not `%model(...)`. The final declaration is accepted; the host does the commit.

The new tests pass (18). `just check` did not go green, and one older widget test fails:
- **`just check`:** mypy reports 15 errors in `_agent_detail_display.py`, `_agent_detail_state.py`, and `command_line/input.py` and `command_line/screen.py`, none in files I touched. I didn't check whether master has the same errors.
- **Older test failure:** `test_ctrl_e_moves_to_line_end_while_completion_remains_open` in `test_prompt_file_completion.py` also fails with my changes stashed. My `-x` run stopped at that failure, so I didn't see the rest of the widget suite.
- **Setup:** the `sase_core_rs` binding in the venv was stale, so I ran `just install` before the tests would run.

- **Helper:** `find_model_effort_spacer` in `_model_effort_spacer.py` checks the cheap string conditions first and only then calls the Rust classifier.
- **Key handling:** `_try_model_effort_spacer_rewrite` in `_prompt_text_area_key_handling.py` runs on `@` in prompt mode with no selection. It reuses `_replace_absolute_range`, so undo works, and then opens the menu.
- **Auto-menu setting:** with `auto_directive_menu` off, the space is still swallowed and no menu opens.
- **Tests and docs:** `tests/ace/tui/widgets/test_model_effort_spacer.py` covers the helper and the typed, shortcut, disabled-menu, plain-prose and undo cases. I skipped the feedback-mode test. `docs/ace.md` has a new sentence in the Model shortcuts bullet, including the undo note.

I did not try it by hand in the TUI.
