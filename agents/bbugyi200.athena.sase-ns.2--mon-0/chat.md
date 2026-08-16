# Chat History - ace-run (sase-ns.2--mon-0)

- **TIMESTAMP:** 2026-08-16 18:20:57 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-ns.2--mon-0

## Prompt

sase monitor start --command 'just test-cost && just selection-health --fail-on-new-flake' --reason 'Full parallel test-cost lane plus flake-baseline check for the config-cache isolation fix. The previous monitor was misquoted (sh -c just) and never ran the suite. just check-full cannot start the suite because of a pre-existing HistoryWordCompletionMetadata mypy error.'

## Response

tests/ace/tui/widgets/test_prompt_star_search.py:8: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
_____ ERROR collecting tests/ace/tui/widgets/test_prompt_stash_capture.py ______
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stash_capture.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stash_capture.py:18: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
__ ERROR collecting tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py __
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
_ ERROR collecting tests/ace/tui/widgets/test_prompt_target_completion_previews.py _
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_target_completion_previews.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_target_completion_previews.py:8: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_labels import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_labels.py:8: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
_____ ERROR collecting tests/ace/tui/widgets/test_prompt_todo_highlight.py _____
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_todo_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_todo_highlight.py:26: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
_______ ERROR collecting tests/ace/tui/widgets/test_prompt_todo_title.py _______
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_todo_title.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_todo_title.py:12: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
____ ERROR collecting tests/ace/tui/widgets/test_prompt_vcs_mru_cycling.py _____
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_vcs_mru_cycling.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_vcs_mru_cycling.py:21: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
______ ERROR collecting tests/ace/tui/widgets/test_prompt_virtual_wrap.py ______
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_virtual_wrap.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_virtual_wrap.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
____ ERROR collecting tests/ace/tui/widgets/test_prompt_word_completion.py _____
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_word_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_word_completion.py:12: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
___ ERROR collecting tests/ace/tui/widgets/test_prompt_xprompt_highlight.py ____
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_xprompt_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_xprompt_highlight.py:16: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
_____ ERROR collecting tests/ace/tui/widgets/test_prompt_yank_highlight.py _____
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_yank_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_yank_highlight.py:16: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
____ ERROR collecting tests/ace/tui/widgets/test_recursive_finder_modal.py _____
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_recursive_finder_modal.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_recursive_finder_modal.py:17: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
_ ERROR collecting tests/ace/tui/widgets/test_snippet_expansion_call_sites.py __
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_snippet_expansion_call_sites.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_snippet_expansion_call_sites.py:7: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
____ ERROR collecting tests/ace/tui/widgets/test_vcs_project_completion.py _____
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_vcs_project_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_vcs_project_completion.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
______ ERROR collecting tests/ace/tui/widgets/test_vcs_ref_completion.py _______
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_vcs_ref_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_vcs_ref_completion.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
______ ERROR collecting tests/ace/tui/widgets/test_vcs_repo_completion.py ______
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_vcs_repo_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_vcs_repo_completion.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
__ ERROR collecting tests/ace/tui/widgets/test_vim_normal_key_containment.py ___
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_vim_normal_key_containment.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_vim_normal_key_containment.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
_______ ERROR collecting tests/ace/tui/widgets/test_xprompt_arg_hints.py _______
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_xprompt_arg_hints.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_xprompt_arg_hints.py:9: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
_ ERROR collecting tests/ace/tui/widgets/test_xprompt_arg_value_completion.py __
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_xprompt_arg_value_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_xprompt_arg_value_completion.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
______ ERROR collecting tests/ace/tui/widgets/test_xprompt_completion.py _______
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_xprompt_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_xprompt_completion.py:8: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
___ ERROR collecting tests/ace/tui/widgets/test_xprompt_completion_spacer.py ___
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_xprompt_completion_spacer.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_xprompt_completion_spacer.py:20: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
__________ ERROR collecting tests/test_prompt_visual_mode_surround.py __________
ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/test_prompt_visual_mode_surround.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/test_prompt_visual_mode_surround.py:9: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
=========================== short test summary info ============================
ERROR tests/ace/tui/actions/test_prompt_save_xprompt.py
ERROR tests/ace/tui/actions/test_prompt_save_xprompt_git.py
ERROR tests/ace/tui/actions/test_prompt_save_xprompt_targets.py
ERROR tests/ace/tui/actions/test_prompt_stash_handler.py
ERROR tests/ace/tui/actions/test_prompt_stash_pump_nonblocking.py
ERROR tests/ace/tui/actions/test_prompt_stash_restore_open.py
ERROR tests/ace/tui/actions/test_prompt_stash_update.py
ERROR tests/ace/tui/test_admin_center_selection_resume.py
ERROR tests/ace/tui/test_agent_bulk_kill_edit.py
ERROR tests/ace/tui/test_entry_points_vcs_prefix_editor_reload.py
ERROR tests/ace/tui/test_event_handlers_artifact_dirty_flags.py
ERROR tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py
ERROR tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py
ERROR tests/ace/tui/test_family_member_relaunch.py
ERROR tests/ace/tui/test_launch_submit_context_release.py
ERROR tests/ace/tui/test_model_completion_panel_titles.py
ERROR tests/ace/tui/test_prompt_bar_editor_stack.py
ERROR tests/ace/tui/test_prompt_bar_history_requests.py
ERROR tests/ace/tui/test_prompt_bar_stack_submit_handlers.py
ERROR tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py
ERROR tests/ace/tui/test_prompt_editor_suspend.py
ERROR tests/ace/tui/test_prompt_input_collection_launch.py
ERROR tests/ace/tui/test_relaunch_prompt_virtual_wrap.py
ERROR tests/ace/tui/test_restart_prompt_stash.py
ERROR tests/ace/tui/test_xprompt_browser_jump.py
ERROR tests/ace/tui/test_xprompt_browser_load_keymap.py
ERROR tests/ace/tui/test_xprompt_target_surface_audit.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_history_word_completion.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_placeholder_completion.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_cursor_readout.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_target_completion.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_word_completion.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_vcs_project_completion.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_vcs_ref_completion.py
ERROR tests/ace/tui/visual/test_ace_png_snapshots_vcs_repo_completion.py
ERROR tests/ace/tui/widgets/test_artifact_ref_completion_widget.py
ERROR tests/ace/tui/widgets/test_at_reference_completion_rendering.py
ERROR tests/ace/tui/widgets/test_auto_xprompt_completion.py
ERROR tests/ace/tui/widgets/test_directive_completion_interactions.py
ERROR tests/ace/tui/widgets/test_file_completion_module.py
ERROR tests/ace/tui/widgets/test_frontmatter_panel.py
ERROR tests/ace/tui/widgets/test_frontmatter_panel_properties.py
ERROR tests/ace/tui/widgets/test_frontmatter_panel_subeditors.py
ERROR tests/ace/tui/widgets/test_history_word_completion.py
ERROR tests/ace/tui/widgets/test_history_word_rows.py
ERROR tests/ace/tui/widgets/test_local_xprompt_completion.py
ERROR tests/ace/tui/widgets/test_model_completion_rows.py
ERROR tests/ace/tui/widgets/test_placeholder_completion.py
ERROR tests/ace/tui/widgets/test_prompt_alt_syntax_editing.py
ERROR tests/ace/tui/widgets/test_prompt_alt_syntax_highlight.py
ERROR tests/ace/tui/widgets/test_prompt_artifact_ref_highlight.py
ERROR tests/ace/tui/widgets/test_prompt_at_prefix_completion.py
ERROR tests/ace/tui/widgets/test_prompt_bar_palette_safety.py
ERROR tests/ace/tui/widgets/test_prompt_bar_xprompt_selector_targeting.py
ERROR tests/ace/tui/widgets/test_prompt_bullet_highlight.py
ERROR tests/ace/tui/widgets/test_prompt_codeblock_highlight.py
ERROR tests/ace/tui/widgets/test_prompt_completion_height.py
ERROR tests/ace/tui/widgets/test_prompt_escape_cancel.py
ERROR tests/ace/tui/widgets/test_prompt_file_completion.py
ERROR tests/ace/tui/widgets/test_prompt_file_history_completion.py
ERROR tests/ace/tui/widgets/test_prompt_format.py
ERROR tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py
ERROR tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py
ERROR tests/ace/tui/widgets/test_prompt_g_prefix_hint_routing.py
ERROR tests/ace/tui/widgets/test_prompt_glossary_highlighting.py
ERROR tests/ace/tui/widgets/test_prompt_history_trigger.py
ERROR tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py
ERROR tests/ace/tui/widgets/test_prompt_input_bar_detach.py
ERROR tests/ace/tui/widgets/test_prompt_input_bar_initial_panes.py
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stack.py
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stack_editor.py
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stack_frontmatter_inputs.py
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stack_xprompt_markdown.py
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stash_load.py
ERROR tests/ace/tui/widgets/test_prompt_jinja.py
ERROR tests/ace/tui/widgets/test_prompt_jinja_pair_editing.py
ERROR tests/ace/tui/widgets/test_prompt_live_completion.py
ERROR tests/ace/tui/widgets/test_prompt_local_xprompt_convert.py
ERROR tests/ace/tui/widgets/test_prompt_ordered_highlight.py
ERROR tests/ace/tui/widgets/test_prompt_pair_editing.py
ERROR tests/ace/tui/widgets/test_prompt_path_inventory.py
ERROR tests/ace/tui/widgets/test_prompt_search_highlight.py
ERROR tests/ace/tui/widgets/test_prompt_search_interactive.py
ERROR tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py
ERROR tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py
ERROR tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py
ERROR tests/ace/tui/widgets/test_prompt_stack_keymaps_separator_vim.py
ERROR tests/ace/tui/widgets/test_prompt_stack_snippet_pane_frame.py
ERROR tests/ace/tui/widgets/test_prompt_stack_snippet_pane_lifecycle.py
ERROR tests/ace/tui/widgets/test_prompt_stack_snippet_pane_model.py
ERROR tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py
ERROR tests/ace/tui/widgets/test_prompt_stack_submit_todo.py
ERROR tests/ace/tui/widgets/test_prompt_stack_subtitles.py
ERROR tests/ace/tui/widgets/test_prompt_star_search.py
ERROR tests/ace/tui/widgets/test_prompt_stash_capture.py
ERROR tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py
ERROR tests/ace/tui/widgets/test_prompt_target_completion_previews.py
ERROR tests/ace/tui/widgets/test_prompt_todo_highlight.py
ERROR tests/ace/tui/widgets/test_prompt_todo_title.py
ERROR tests/ace/tui/widgets/test_prompt_vcs_mru_cycling.py
ERROR tests/ace/tui/widgets/test_prompt_virtual_wrap.py
ERROR tests/ace/tui/widgets/test_prompt_word_completion.py
ERROR tests/ace/tui/widgets/test_prompt_xprompt_highlight.py
ERROR tests/ace/tui/widgets/test_prompt_yank_highlight.py
ERROR tests/ace/tui/widgets/test_recursive_finder_modal.py
ERROR tests/ace/tui/widgets/test_snippet_expansion_call_sites.py
ERROR tests/ace/tui/widgets/test_vcs_project_completion.py
ERROR tests/ace/tui/widgets/test_vcs_ref_completion.py
ERROR tests/ace/tui/widgets/test_vcs_repo_completion.py
ERROR tests/ace/tui/widgets/test_vim_normal_key_containment.py
ERROR tests/ace/tui/widgets/test_xprompt_arg_hints.py
ERROR tests/ace/tui/widgets/test_xprompt_arg_value_completion.py
ERROR tests/ace/tui/widgets/test_xprompt_completion.py
ERROR tests/ace/tui/widgets/test_xprompt_completion_spacer.py
ERROR tests/test_prompt_visual_mode_surround.py
!!!!!!!!!!!!!!!!!! Interrupted: 121 errors during collection !!!!!!!!!!!!!!!!!!!
451/30717 tests collected (30266 deselected), 121 errors in 22.30s
------------------------------ Captured log call -------------------------------
WARNING  sase.config.loading:loading.py:135 Ignoring owner identity key(s) id from non-authoritative config source /home/bryan/.config/sase/sase_athena.yml; run `sase config init` to manage identity in the selected machine overlay
WARNING  sase.config.loading:loading.py:135 Ignoring owner identity key(s) id from non-authoritative config source /home/bryan/.config/sase/sase_athena.yml; run `sase config init` to manage identity in the selected machine overlay
___________ test_unmount_after_submit_skips_cancel_save_and_detaches ___________
[gw4] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    def test_unmount_after_submit_skips_cancel_save_and_detaches() -> None:
        """The submit unmount detaches the bar but does NOT save as cancelled."""
        bar = object()
        harness = _MountHarness(bar)
    
>       harness._unmount_prompt_bar_after_submit()

tests/ace/tui/test_prompt_bar_submit_no_cancel_save.py:99: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:206: in _unmount_prompt_bar_after_submit
    self._unmount_prompt_bar_without_cancel_save()
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:210: in _unmount_prompt_bar_without_cancel_save
    from ...widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
______________ test_cancel_unmount_still_saves_text_as_cancelled _______________
[gw4] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    def test_cancel_unmount_still_saves_text_as_cancelled() -> None:
        """The cancel/dismiss path must still call the safety-net save."""
        bar = object()
        harness = _MountHarness(bar)
    
>       stored = harness._unmount_prompt_bar()
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_prompt_bar_submit_no_cancel_save.py:110: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:184: in _unmount_prompt_bar
    from ...widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
____________ test_unmount_after_submit_is_noop_when_no_bar_mounted _____________
[gw4] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    def test_unmount_after_submit_is_noop_when_no_bar_mounted() -> None:
        """Missing bar must not raise — same contract as cancel-path unmount."""
        harness = _MountHarness(bar=None)
    
>       harness._unmount_prompt_bar_after_submit()

tests/ace/tui/test_prompt_bar_submit_no_cancel_save.py:121: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:206: in _unmount_prompt_bar_after_submit
    self._unmount_prompt_bar_without_cancel_save()
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:210: in _unmount_prompt_bar_without_cancel_save
    from ...widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
_______________ test_unmount_prompt_bar_propagates_recorded_text _______________
[gw4] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    def test_unmount_prompt_bar_propagates_recorded_text() -> None:
        bar = _Bar("fix the auth bug today")
        harness = _RealSaveHarness(bar)
    
        with (
            patch("sase.history.prompt.add_or_update_prompt"),
            patch(
                "sase.history.file_references.extract_recordable_file_refs",
                return_value=[],
            ),
        ):
>           stored = harness._unmount_prompt_bar()
                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_prompt_bar_submit_no_cancel_save.py:211: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:184: in _unmount_prompt_bar
    from ...widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
______ test_ace_page_group_reuses_page_and_resets_prompt_without_history _______
[gw9] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    async def test_ace_page_group_reuses_page_and_resets_prompt_without_history() -> None:
        with (
            patch("sase.config.load_merged_config", return_value={"ace": {}}),
            patch("sase.history.prompt.add_or_update_prompt") as save_history,
        ):
            async with AcePageGroup() as group:
                async with group.checkout() as page:
                    app = page.app
>                   app._show_prompt_input_bar_for_home(initial_text="hello")

tests/test_ace_testing.py:444: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:378: in _show_prompt_input_bar_for_home
    from ...widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError

During handling of the above exception, another exception occurred:

    async def test_ace_page_group_reuses_page_and_resets_prompt_without_history() -> None:
        with (
            patch("sase.config.load_merged_config", return_value={"ace": {}}),
            patch("sase.history.prompt.add_or_update_prompt") as save_history,
        ):
            async with AcePageGroup() as group:
>               async with group.checkout() as page:
                           ^^^^^^^^^^^^^^^^

tests/test_ace_testing.py:442: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/contextlib.py:235: in __aexit__
    await self.gen.athrow(value)
src/sase/ace/testing/ace_page_group.py:144: in checkout
    await self._reset_shared_page(shared_page)
src/sase/ace/testing/ace_page_group.py:167: in _reset_shared_page
    _remove_prompt_surfaces(app)
src/sase/ace/testing/ace_page_group.py:237: in _remove_prompt_surfaces
    unmount_prompt()
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:210: in _unmount_prompt_bar_without_cancel_save
    from ...widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
______________ test_ace_page_group_rejects_overlapping_checkouts _______________
[gw9] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    async def test_ace_page_group_rejects_overlapping_checkouts() -> None:
        async with AcePageGroup() as group:
            checkout = group.checkout()
            await checkout.__aenter__()
            try:
                with pytest.raises(RuntimeError, match="overlapping checkouts"):
                    async with group.checkout():
                        pass
            finally:
>               await checkout.__aexit__(None, None, None)

tests/test_ace_testing.py:464: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/contextlib.py:221: in __aexit__
    await anext(self.gen)
src/sase/ace/testing/ace_page_group.py:144: in checkout
    await self._reset_shared_page(shared_page)
src/sase/ace/testing/ace_page_group.py:167: in _reset_shared_page
    _remove_prompt_surfaces(app)
src/sase/ace/testing/ace_page_group.py:237: in _remove_prompt_surfaces
    unmount_prompt()
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:210: in _unmount_prompt_bar_without_cancel_save
    from ...widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
_________________ test_ace_page_group_reports_reset_hook_leaks _________________
[gw9] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    async def test_ace_page_group_reports_reset_hook_leaks() -> None:
        def leak(page: AcePage) -> None:
            page.app.current_idx = 1
    
        async with AcePageGroup(reset_hook=leak) as group:
            with pytest.raises(AssertionError, match="idx"):
>               async with group.checkout():
                           ^^^^^^^^^^^^^^^^

tests/test_ace_testing.py:473: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/contextlib.py:221: in __aexit__
    await anext(self.gen)
src/sase/ace/testing/ace_page_group.py:144: in checkout
    await self._reset_shared_page(shared_page)
src/sase/ace/testing/ace_page_group.py:167: in _reset_shared_page
    _remove_prompt_surfaces(app)
src/sase/ace/testing/ace_page_group.py:237: in _remove_prompt_surfaces
    unmount_prompt()
src/sase/ace/tui/actions/agent_workflow/_prompt_bar_mount.py:210: in _unmount_prompt_bar_without_cancel_save
    from ...widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
________________________ test_prompt_page_initial_state ________________________
[gw9] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    async def test_prompt_page_initial_state() -> None:
        """PromptPage sets text, cursor, and mode on entry."""
>       async with PromptPage("hello world", cursor=(0, 5)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_ace_testing.py:544: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/editors.py:104: in __aenter__
    self._ta._enter_normal_mode()
src/sase/ace/tui/widgets/_prompt_text_area_actions.py:233: in _enter_normal_mode
    super()._enter_normal_mode()
src/sase/ace/tui/widgets/vim_text_area.py:208: in _enter_normal_mode
    self._update_vim_mode_display()
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:78: in _update_vim_mode_display
    bar = self._find_prompt_bar()
          ^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:37: in _find_prompt_bar
    PromptInputBar = prompt_bar_class()
                     ^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:22: in prompt_bar_class
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
--------------------------- Captured stderr teardown ---------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_actions.py:254 in _on_resize                   │
│                                                                              │
│   251 │   │   """Scroll cursor into view after the parent resizes."""        │
│   252 │   │   super()._on_resize()                                           │
│   253 │   │   self.call_after_refresh(self.scroll_cursor_visible)            │
│ ❱ 254 │   │   bar = self._find_prompt_bar()                                  │
│   255 │   │   if bar:                                                        │
│   256 │   │   │   bar._schedule_height_update()                              │
│   257                                                                        │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:37 in _find_prompt_bar                  │
│                                                                              │
│    34 │                                                                      │
│    35 │   def _find_prompt_bar(self) -> Any:                                 │
│    36 │   │   """Walk up the widget tree to find the parent PromptInputBar." │
│ ❱  37 │   │   PromptInputBar = prompt_bar_class()                            │
│    38 │   │   parent = self.parent                                           │
│    39 │   │   while parent is not None:                                      │
│    40 │   │   │   if isinstance(parent, PromptInputBar):                     │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:22 in prompt_bar_class                  │
│                                                                              │
│    19                                                                        │
│    20 def prompt_bar_class() -> type[PromptInputBar]:                        │
│    21 │   """Lazy import to avoid circular dependency with prompt_input_bar. │
│ ❱  22 │   from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar   │
│    23 │                                                                      │
│    24 │   return PromptInputBar                                              │
│    25                                                                        │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/prompt_input_bar.py:18 in <module>                               │
│                                                                              │
│    15 from sase.ace.tui.widgets._prompt_input_bar_actions import (           │
│    16 │   PromptInputBarActionsMixin,                                        │
│    17 )                                                                      │
│ ❱  18 from sase.ace.tui.widgets._prompt_input_bar_completion import (        │
│    19 │   PromptInputBarCompletionMixin,                                     │
│    20 )                                                                      │
│    21 from sase.ace.tui.widgets._prompt_input_bar_frontmatter import (       │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ ComposeResult = typing.Iterable[textual.widget.Widget]         │           │
│ │          time = <module 'time' (built-in)>                     │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion.py:5 in <module>                    │
│                                                                              │
│    2                                                                         │
│    3 from __future__ import annotations                                      │
│    4                                                                         │
│ ❱  5 from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (   │
│    6 │   PromptInputBarCompletionMixin,                                      │
│    7 )                                                                       │
│    8                                                                         │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel.py:22 in <module>             │
│                                                                              │
│    19 │   cursor_readout_position,                                           │
│    20 │   format_cursor_readout,                                             │
│    21 )                                                                      │
│ ❱  22 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content i │
│    23 │   build_completion_panel_content,                                    │
│    24 )                                                                      │
│    25 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ TYPE_CHECKING = False                                          │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_content.py:12 in <module>     │
│                                                                              │
│     9                                                                        │
│    10 from sase.ace.tui.agent_completion import AgentCompletionCandidate     │
│    11 from sase.ace.tui.models.tribe_display import named_tribe_identity_col │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│    13 │   CompletionPanelKinds,                                              │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12 in <module>       │
│                                                                              │
│     9                                                                        │
│    10 from dataclasses import dataclass                                      │
│    11                                                                        │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│    13 │   is_agent_completion_candidate,                                     │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets.artifact_ref_completion import (             │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_rows.py:7 in <module>               │
│                                                                              │
│    4 original import surface for the completion panel and focused rendering  │
│    5 """                                                                     │
│    6                                                                         │
│ ❱  7 from sase.ace.tui.widgets._history_word_rows import (                   │
│    8 │   append_history_word_completion_row,                                 │
│    9 │   history_word_label_width,                                           │
│   10 )                                                                       │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_history_word_rows.py:17 in <module>                             │
│                                                                              │
│    14 │   truncate_cell,                                                     │
│    15 )                                                                      │
│    16 from sase.ace.tui.widgets.file_completion import CompletionCandidate   │
│ ❱  17 from sase.ace.tui.widgets.history_word_completion import (             │
│    18 │   HistoryWordCompletionMetadata,                                     │
│    19 │   HistoryWordCompletionPlaceholder,                                  │
│    20 )                                                                      │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ │        math = <module 'math' (built-in)>                     │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
╰──────────────────────────────────────────────────────────────────────────────╯
ImportError: cannot import name 'HistoryWordCompletionMetadata' from 
'sase.ace.tui.widgets.history_word_completion' 
(/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui
/widgets/history_word_completion.py)
---------------------------- Captured log teardown -----------------------------
ERROR    asyncio:base_events.py:1875 an error occurred during closing of asynchronous generator <async_generator object App.run_test at 0x7fd3e7398190>
asyncgen: <async_generator object App.run_test at 0x7fd3e7398190>
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2137, in run_test
    yield pilot
GeneratorExit

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 1053, in _context
    yield
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2145, in run_test
    raise self._exception
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 654, in _process_messages_loop
    await self._dispatch_message(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 718, in _dispatch_message
    await self.on_event(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 799, in on_event
    await self._on_message(event)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 820, in _on_message
    await invoke(method, message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_actions.py", line 254, in _on_resize
    bar = self._find_prompt_bar()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_bar.py", line 37, in _find_prompt_bar
    PromptInputBar = prompt_bar_class()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_bar.py", line 22, in prompt_bar_class
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/prompt_input_bar.py", line 18, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
        PromptInputBarCompletionMixin,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion.py", line 5, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
        PromptInputBarCompletionMixin,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py", line 22, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
        build_completion_panel_content,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py", line 12, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
        CompletionPanelKinds,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py", line 12, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
        is_agent_completion_candidate,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py", line 7, in <module>
    from sase.ace.tui.widgets._history_word_rows import (
    ...<2 lines>...
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_history_word_rows.py", line 17, in <module>
    from sase.ace.tui.widgets.history_word_completion import (
    ...<2 lines>...
    )
ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2132, in run_test
    with app._context():
         ~~~~~~~~~~~~^^
  File "/home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 162, in __exit__
    self.gen.throw(value)
    ~~~~~~~~~~~~~~^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 1055, in _context
    active_message_pump.reset(message_pump_reset_token)
    ~~~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^
ValueError: <Token var=<ContextVar name='active_message_pump' at 0x7fd403dfc7c0> at 0x7fd3e434e140> was created in a different Context
____________________________ test_prompt_page_press ____________________________
[gw9] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    async def test_prompt_page_press() -> None:
        """Pressing keys through PromptPage works."""
>       async with PromptPage("one two three", cursor=(0, 0)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_ace_testing.py:552: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/editors.py:104: in __aenter__
    self._ta._enter_normal_mode()
src/sase/ace/tui/widgets/_prompt_text_area_actions.py:233: in _enter_normal_mode
    super()._enter_normal_mode()
src/sase/ace/tui/widgets/vim_text_area.py:208: in _enter_normal_mode
    self._update_vim_mode_display()
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:78: in _update_vim_mode_display
    bar = self._find_prompt_bar()
          ^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:37: in _find_prompt_bar
    PromptInputBar = prompt_bar_class()
                     ^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:22: in prompt_bar_class
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
--------------------------- Captured stderr teardown ---------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_actions.py:254 in _on_resize                   │
│                                                                              │
│   251 │   │   """Scroll cursor into view after the parent resizes."""        │
│   252 │   │   super()._on_resize()                                           │
│   253 │   │   self.call_after_refresh(self.scroll_cursor_visible)            │
│ ❱ 254 │   │   bar = self._find_prompt_bar()                                  │
│   255 │   │   if bar:                                                        │
│   256 │   │   │   bar._schedule_height_update()                              │
│   257                                                                        │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:37 in _find_prompt_bar                  │
│                                                                              │
│    34 │                                                                      │
│    35 │   def _find_prompt_bar(self) -> Any:                                 │
│    36 │   │   """Walk up the widget tree to find the parent PromptInputBar." │
│ ❱  37 │   │   PromptInputBar = prompt_bar_class()                            │
│    38 │   │   parent = self.parent                                           │
│    39 │   │   while parent is not None:                                      │
│    40 │   │   │   if isinstance(parent, PromptInputBar):                     │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:22 in prompt_bar_class                  │
│                                                                              │
│    19                                                                        │
│    20 def prompt_bar_class() -> type[PromptInputBar]:                        │
│    21 │   """Lazy import to avoid circular dependency with prompt_input_bar. │
│ ❱  22 │   from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar   │
│    23 │                                                                      │
│    24 │   return PromptInputBar                                              │
│    25                                                                        │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/prompt_input_bar.py:18 in <module>                               │
│                                                                              │
│    15 from sase.ace.tui.widgets._prompt_input_bar_actions import (           │
│    16 │   PromptInputBarActionsMixin,                                        │
│    17 )                                                                      │
│ ❱  18 from sase.ace.tui.widgets._prompt_input_bar_completion import (        │
│    19 │   PromptInputBarCompletionMixin,                                     │
│    20 )                                                                      │
│    21 from sase.ace.tui.widgets._prompt_input_bar_frontmatter import (       │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ ComposeResult = typing.Iterable[textual.widget.Widget]         │           │
│ │          time = <module 'time' (built-in)>                     │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion.py:5 in <module>                    │
│                                                                              │
│    2                                                                         │
│    3 from __future__ import annotations                                      │
│    4                                                                         │
│ ❱  5 from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (   │
│    6 │   PromptInputBarCompletionMixin,                                      │
│    7 )                                                                       │
│    8                                                                         │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel.py:22 in <module>             │
│                                                                              │
│    19 │   cursor_readout_position,                                           │
│    20 │   format_cursor_readout,                                             │
│    21 )                                                                      │
│ ❱  22 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content i │
│    23 │   build_completion_panel_content,                                    │
│    24 )                                                                      │
│    25 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ TYPE_CHECKING = False                                          │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_content.py:12 in <module>     │
│                                                                              │
│     9                                                                        │
│    10 from sase.ace.tui.agent_completion import AgentCompletionCandidate     │
│    11 from sase.ace.tui.models.tribe_display import named_tribe_identity_col │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│    13 │   CompletionPanelKinds,                                              │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12 in <module>       │
│                                                                              │
│     9                                                                        │
│    10 from dataclasses import dataclass                                      │
│    11                                                                        │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│    13 │   is_agent_completion_candidate,                                     │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets.artifact_ref_completion import (             │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_rows.py:7 in <module>               │
│                                                                              │
│    4 original import surface for the completion panel and focused rendering  │
│    5 """                                                                     │
│    6                                                                         │
│ ❱  7 from sase.ace.tui.widgets._history_word_rows import (                   │
│    8 │   append_history_word_completion_row,                                 │
│    9 │   history_word_label_width,                                           │
│   10 )                                                                       │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_history_word_rows.py:17 in <module>                             │
│                                                                              │
│    14 │   truncate_cell,                                                     │
│    15 )                                                                      │
│    16 from sase.ace.tui.widgets.file_completion import CompletionCandidate   │
│ ❱  17 from sase.ace.tui.widgets.history_word_completion import (             │
│    18 │   HistoryWordCompletionMetadata,                                     │
│    19 │   HistoryWordCompletionPlaceholder,                                  │
│    20 )                                                                      │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ │        math = <module 'math' (built-in)>                     │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
╰──────────────────────────────────────────────────────────────────────────────╯
ImportError: cannot import name 'HistoryWordCompletionMetadata' from 
'sase.ace.tui.widgets.history_word_completion' 
(/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui
/widgets/history_word_completion.py)
---------------------------- Captured log teardown -----------------------------
ERROR    asyncio:base_events.py:1875 an error occurred during closing of asynchronous generator <async_generator object App.run_test at 0x7fd3e6f8dbd0>
asyncgen: <async_generator object App.run_test at 0x7fd3e6f8dbd0>
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2137, in run_test
    yield pilot
GeneratorExit

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 1053, in _context
    yield
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2145, in run_test
    raise self._exception
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 654, in _process_messages_loop
    await self._dispatch_message(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 718, in _dispatch_message
    await self.on_event(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 799, in on_event
    await self._on_message(event)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 820, in _on_message
    await invoke(method, message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_actions.py", line 254, in _on_resize
    bar = self._find_prompt_bar()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_bar.py", line 37, in _find_prompt_bar
    PromptInputBar = prompt_bar_class()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_bar.py", line 22, in prompt_bar_class
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/prompt_input_bar.py", line 18, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
        PromptInputBarCompletionMixin,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion.py", line 5, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
        PromptInputBarCompletionMixin,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py", line 22, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
        build_completion_panel_content,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py", line 12, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
        CompletionPanelKinds,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py", line 12, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
        is_agent_completion_candidate,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py", line 7, in <module>
    from sase.ace.tui.widgets._history_word_rows import (
    ...<2 lines>...
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_history_word_rows.py", line 17, in <module>
    from sase.ace.tui.widgets.history_word_completion import (
    ...<2 lines>...
    )
ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2132, in run_test
    with app._context():
         ~~~~~~~~~~~~^^
  File "/home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 162, in __exit__
    self.gen.throw(value)
    ~~~~~~~~~~~~~~^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 1055, in _context
    active_message_pump.reset(message_pump_reset_token)
    ~~~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^
ValueError: <Token var=<ContextVar name='active_message_pump' at 0x7fd403dfc7c0> at 0x7fd3dd268940> was created in a different Context
_________________________ test_prompt_page_insert_mode _________________________
[gw9] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    async def test_prompt_page_insert_mode() -> None:
        """PromptPage with mode='insert' does not enter normal mode."""
>       async with PromptPage("hello", mode="insert") as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_ace_testing.py:559: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/editors.py:114: in __aexit__
    await self._pilot_cm.__aexit__(exc_type, exc_val, exc_tb)
tests/_test_cost_plugin.py:47: in __aexit__
    return await self._wrapped.__aexit__(*args)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/contextlib.py:221: in __aexit__
    await anext(self.gen)
.venv/lib/python3.14/site-packages/textual/app.py:2145: in run_test
    raise self._exception
.venv/lib/python3.14/site-packages/textual/message_pump.py:654: in _process_messages_loop
    await self._dispatch_message(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:718: in _dispatch_message
    await self.on_event(message)
.venv/lib/python3.14/site-packages/textual/message_pump.py:799: in on_event
    await self._on_message(event)
.venv/lib/python3.14/site-packages/textual/message_pump.py:820: in _on_message
    await invoke(method, message)
.venv/lib/python3.14/site-packages/textual/_callback.py:96: in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
.venv/lib/python3.14/site-packages/textual/_callback.py:56: in _invoke
    result = callback(*params[:parameter_count])
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_actions.py:254: in _on_resize
    bar = self._find_prompt_bar()
          ^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:37: in _find_prompt_bar
    PromptInputBar = prompt_bar_class()
                     ^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:22: in prompt_bar_class
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
----------------------------- Captured stderr call -----------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_actions.py:254 in _on_resize                   │
│                                                                              │
│   251 │   │   """Scroll cursor into view after the parent resizes."""        │
│   252 │   │   super()._on_resize()                                           │
│   253 │   │   self.call_after_refresh(self.scroll_cursor_visible)            │
│ ❱ 254 │   │   bar = self._find_prompt_bar()                                  │
│   255 │   │   if bar:                                                        │
│   256 │   │   │   bar._schedule_height_update()                              │
│   257                                                                        │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:37 in _find_prompt_bar                  │
│                                                                              │
│    34 │                                                                      │
│    35 │   def _find_prompt_bar(self) -> Any:                                 │
│    36 │   │   """Walk up the widget tree to find the parent PromptInputBar." │
│ ❱  37 │   │   PromptInputBar = prompt_bar_class()                            │
│    38 │   │   parent = self.parent                                           │
│    39 │   │   while parent is not None:                                      │
│    40 │   │   │   if isinstance(parent, PromptInputBar):                     │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:22 in prompt_bar_class                  │
│                                                                              │
│    19                                                                        │
│    20 def prompt_bar_class() -> type[PromptInputBar]:                        │
│    21 │   """Lazy import to avoid circular dependency with prompt_input_bar. │
│ ❱  22 │   from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar   │
│    23 │                                                                      │
│    24 │   return PromptInputBar                                              │
│    25                                                                        │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/prompt_input_bar.py:18 in <module>                               │
│                                                                              │
│    15 from sase.ace.tui.widgets._prompt_input_bar_actions import (           │
│    16 │   PromptInputBarActionsMixin,                                        │
│    17 )                                                                      │
│ ❱  18 from sase.ace.tui.widgets._prompt_input_bar_completion import (        │
│    19 │   PromptInputBarCompletionMixin,                                     │
│    20 )                                                                      │
│    21 from sase.ace.tui.widgets._prompt_input_bar_frontmatter import (       │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ ComposeResult = typing.Iterable[textual.widget.Widget]         │           │
│ │          time = <module 'time' (built-in)>                     │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion.py:5 in <module>                    │
│                                                                              │
│    2                                                                         │
│    3 from __future__ import annotations                                      │
│    4                                                                         │
│ ❱  5 from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (   │
│    6 │   PromptInputBarCompletionMixin,                                      │
│    7 )                                                                       │
│    8                                                                         │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel.py:22 in <module>             │
│                                                                              │
│    19 │   cursor_readout_position,                                           │
│    20 │   format_cursor_readout,                                             │
│    21 )                                                                      │
│ ❱  22 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content i │
│    23 │   build_completion_panel_content,                                    │
│    24 )                                                                      │
│    25 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ TYPE_CHECKING = False                                          │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_content.py:12 in <module>     │
│                                                                              │
│     9                                                                        │
│    10 from sase.ace.tui.agent_completion import AgentCompletionCandidate     │
│    11 from sase.ace.tui.models.tribe_display import named_tribe_identity_col │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│    13 │   CompletionPanelKinds,                                              │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12 in <module>       │
│                                                                              │
│     9                                                                        │
│    10 from dataclasses import dataclass                                      │
│    11                                                                        │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│    13 │   is_agent_completion_candidate,                                     │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets.artifact_ref_completion import (             │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_rows.py:7 in <module>               │
│                                                                              │
│    4 original import surface for the completion panel and focused rendering  │
│    5 """                                                                     │
│    6                                                                         │
│ ❱  7 from sase.ace.tui.widgets._history_word_rows import (                   │
│    8 │   append_history_word_completion_row,                                 │
│    9 │   history_word_label_width,                                           │
│   10 )                                                                       │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_history_word_rows.py:17 in <module>                             │
│                                                                              │
│    14 │   truncate_cell,                                                     │
│    15 )                                                                      │
│    16 from sase.ace.tui.widgets.file_completion import CompletionCandidate   │
│ ❱  17 from sase.ace.tui.widgets.history_word_completion import (             │
│    18 │   HistoryWordCompletionMetadata,                                     │
│    19 │   HistoryWordCompletionPlaceholder,                                  │
│    20 )                                                                      │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ │        math = <module 'math' (built-in)>                     │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
╰──────────────────────────────────────────────────────────────────────────────╯
ImportError: cannot import name 'HistoryWordCompletionMetadata' from 
'sase.ace.tui.widgets.history_word_completion' 
(/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui
/widgets/history_word_completion.py)
__________________________ test_prompt_page_ta_access __________________________
[gw9] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    async def test_prompt_page_ta_access() -> None:
        """page.ta gives direct access to the PromptTextArea widget."""
>       async with PromptPage("test") as page:
                   ^^^^^^^^^^^^^^^^^^

tests/test_ace_testing.py:565: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/editors.py:104: in __aenter__
    self._ta._enter_normal_mode()
src/sase/ace/tui/widgets/_prompt_text_area_actions.py:233: in _enter_normal_mode
    super()._enter_normal_mode()
src/sase/ace/tui/widgets/vim_text_area.py:208: in _enter_normal_mode
    self._update_vim_mode_display()
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:78: in _update_vim_mode_display
    bar = self._find_prompt_bar()
          ^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:37: in _find_prompt_bar
    PromptInputBar = prompt_bar_class()
                     ^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:22: in prompt_bar_class
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
--------------------------- Captured stderr teardown ---------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_actions.py:254 in _on_resize                   │
│                                                                              │
│   251 │   │   """Scroll cursor into view after the parent resizes."""        │
│   252 │   │   super()._on_resize()                                           │
│   253 │   │   self.call_after_refresh(self.scroll_cursor_visible)            │
│ ❱ 254 │   │   bar = self._find_prompt_bar()                                  │
│   255 │   │   if bar:                                                        │
│   256 │   │   │   bar._schedule_height_update()                              │
│   257                                                                        │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:37 in _find_prompt_bar                  │
│                                                                              │
│    34 │                                                                      │
│    35 │   def _find_prompt_bar(self) -> Any:                                 │
│    36 │   │   """Walk up the widget tree to find the parent PromptInputBar." │
│ ❱  37 │   │   PromptInputBar = prompt_bar_class()                            │
│    38 │   │   parent = self.parent                                           │
│    39 │   │   while parent is not None:                                      │
│    40 │   │   │   if isinstance(parent, PromptInputBar):                     │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:22 in prompt_bar_class                  │
│                                                                              │
│    19                                                                        │
│    20 def prompt_bar_class() -> type[PromptInputBar]:                        │
│    21 │   """Lazy import to avoid circular dependency with prompt_input_bar. │
│ ❱  22 │   from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar   │
│    23 │                                                                      │
│    24 │   return PromptInputBar                                              │
│    25                                                                        │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/prompt_input_bar.py:18 in <module>                               │
│                                                                              │
│    15 from sase.ace.tui.widgets._prompt_input_bar_actions import (           │
│    16 │   PromptInputBarActionsMixin,                                        │
│    17 )                                                                      │
│ ❱  18 from sase.ace.tui.widgets._prompt_input_bar_completion import (        │
│    19 │   PromptInputBarCompletionMixin,                                     │
│    20 )                                                                      │
│    21 from sase.ace.tui.widgets._prompt_input_bar_frontmatter import (       │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ ComposeResult = typing.Iterable[textual.widget.Widget]         │           │
│ │          time = <module 'time' (built-in)>                     │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion.py:5 in <module>                    │
│                                                                              │
│    2                                                                         │
│    3 from __future__ import annotations                                      │
│    4                                                                         │
│ ❱  5 from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (   │
│    6 │   PromptInputBarCompletionMixin,                                      │
│    7 )                                                                       │
│    8                                                                         │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel.py:22 in <module>             │
│                                                                              │
│    19 │   cursor_readout_position,                                           │
│    20 │   format_cursor_readout,                                             │
│    21 )                                                                      │
│ ❱  22 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content i │
│    23 │   build_completion_panel_content,                                    │
│    24 )                                                                      │
│    25 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ TYPE_CHECKING = False                                          │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_content.py:12 in <module>     │
│                                                                              │
│     9                                                                        │
│    10 from sase.ace.tui.agent_completion import AgentCompletionCandidate     │
│    11 from sase.ace.tui.models.tribe_display import named_tribe_identity_col │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│    13 │   CompletionPanelKinds,                                              │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12 in <module>       │
│                                                                              │
│     9                                                                        │
│    10 from dataclasses import dataclass                                      │
│    11                                                                        │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│    13 │   is_agent_completion_candidate,                                     │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets.artifact_ref_completion import (             │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_rows.py:7 in <module>               │
│                                                                              │
│    4 original import surface for the completion panel and focused rendering  │
│    5 """                                                                     │
│    6                                                                         │
│ ❱  7 from sase.ace.tui.widgets._history_word_rows import (                   │
│    8 │   append_history_word_completion_row,                                 │
│    9 │   history_word_label_width,                                           │
│   10 )                                                                       │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_history_word_rows.py:17 in <module>                             │
│                                                                              │
│    14 │   truncate_cell,                                                     │
│    15 )                                                                      │
│    16 from sase.ace.tui.widgets.file_completion import CompletionCandidate   │
│ ❱  17 from sase.ace.tui.widgets.history_word_completion import (             │
│    18 │   HistoryWordCompletionMetadata,                                     │
│    19 │   HistoryWordCompletionPlaceholder,                                  │
│    20 )                                                                      │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ │        math = <module 'math' (built-in)>                     │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
╰──────────────────────────────────────────────────────────────────────────────╯
ImportError: cannot import name 'HistoryWordCompletionMetadata' from 
'sase.ace.tui.widgets.history_word_completion' 
(/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui
/widgets/history_word_completion.py)
---------------------------- Captured log teardown -----------------------------
ERROR    asyncio:base_events.py:1875 an error occurred during closing of asynchronous generator <async_generator object App.run_test at 0x7fd3e2048d60>
asyncgen: <async_generator object App.run_test at 0x7fd3e2048d60>
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2137, in run_test
    yield pilot
GeneratorExit

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 1053, in _context
    yield
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2145, in run_test
    raise self._exception
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 654, in _process_messages_loop
    await self._dispatch_message(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 718, in _dispatch_message
    await self.on_event(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 799, in on_event
    await self._on_message(event)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 820, in _on_message
    await invoke(method, message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_actions.py", line 254, in _on_resize
    bar = self._find_prompt_bar()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_bar.py", line 37, in _find_prompt_bar
    PromptInputBar = prompt_bar_class()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_bar.py", line 22, in prompt_bar_class
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/prompt_input_bar.py", line 18, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
        PromptInputBarCompletionMixin,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion.py", line 5, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
        PromptInputBarCompletionMixin,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py", line 22, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
        build_completion_panel_content,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py", line 12, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
        CompletionPanelKinds,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py", line 12, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
        is_agent_completion_candidate,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py", line 7, in <module>
    from sase.ace.tui.widgets._history_word_rows import (
    ...<2 lines>...
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_history_word_rows.py", line 17, in <module>
    from sase.ace.tui.widgets.history_word_completion import (
    ...<2 lines>...
    )
ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2132, in run_test
    with app._context():
         ~~~~~~~~~~~~^^
  File "/home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 162, in __exit__
    self.gen.throw(value)
    ~~~~~~~~~~~~~~^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 1055, in _context
    active_message_pump.reset(message_pump_reset_token)
    ~~~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^
ValueError: <Token var=<ContextVar name='active_message_pump' at 0x7fd403dfc7c0> at 0x7fd3dd3dfd40> was created in a different Context
________________________ test_prompt_page_cursor_setter ________________________
[gw9] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    async def test_prompt_page_cursor_setter() -> None:
        """page.cursor can be set mid-test."""
>       async with PromptPage("hello\nworld", cursor=(0, 0)) as page:
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/test_ace_testing.py:572: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/editors.py:104: in __aenter__
    self._ta._enter_normal_mode()
src/sase/ace/tui/widgets/_prompt_text_area_actions.py:233: in _enter_normal_mode
    super()._enter_normal_mode()
src/sase/ace/tui/widgets/vim_text_area.py:208: in _enter_normal_mode
    self._update_vim_mode_display()
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:78: in _update_vim_mode_display
    bar = self._find_prompt_bar()
          ^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:37: in _find_prompt_bar
    PromptInputBar = prompt_bar_class()
                     ^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/_prompt_text_area_bar.py:22: in prompt_bar_class
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
--------------------------- Captured stderr teardown ---------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_actions.py:254 in _on_resize                   │
│                                                                              │
│   251 │   │   """Scroll cursor into view after the parent resizes."""        │
│   252 │   │   super()._on_resize()                                           │
│   253 │   │   self.call_after_refresh(self.scroll_cursor_visible)            │
│ ❱ 254 │   │   bar = self._find_prompt_bar()                                  │
│   255 │   │   if bar:                                                        │
│   256 │   │   │   bar._schedule_height_update()                              │
│   257                                                                        │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:37 in _find_prompt_bar                  │
│                                                                              │
│    34 │                                                                      │
│    35 │   def _find_prompt_bar(self) -> Any:                                 │
│    36 │   │   """Walk up the widget tree to find the parent PromptInputBar." │
│ ❱  37 │   │   PromptInputBar = prompt_bar_class()                            │
│    38 │   │   parent = self.parent                                           │
│    39 │   │   while parent is not None:                                      │
│    40 │   │   │   if isinstance(parent, PromptInputBar):                     │
│                                                                              │
│ ╭─────────────────────── locals ────────────────────────╮                    │
│ │ self = PromptTextArea(id='ta', classes='-vim-insert') │                    │
│ ╰───────────────────────────────────────────────────────╯                    │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_text_area_bar.py:22 in prompt_bar_class                  │
│                                                                              │
│    19                                                                        │
│    20 def prompt_bar_class() -> type[PromptInputBar]:                        │
│    21 │   """Lazy import to avoid circular dependency with prompt_input_bar. │
│ ❱  22 │   from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar   │
│    23 │                                                                      │
│    24 │   return PromptInputBar                                              │
│    25                                                                        │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/prompt_input_bar.py:18 in <module>                               │
│                                                                              │
│    15 from sase.ace.tui.widgets._prompt_input_bar_actions import (           │
│    16 │   PromptInputBarActionsMixin,                                        │
│    17 )                                                                      │
│ ❱  18 from sase.ace.tui.widgets._prompt_input_bar_completion import (        │
│    19 │   PromptInputBarCompletionMixin,                                     │
│    20 )                                                                      │
│    21 from sase.ace.tui.widgets._prompt_input_bar_frontmatter import (       │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ ComposeResult = typing.Iterable[textual.widget.Widget]         │           │
│ │          time = <module 'time' (built-in)>                     │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion.py:5 in <module>                    │
│                                                                              │
│    2                                                                         │
│    3 from __future__ import annotations                                      │
│    4                                                                         │
│ ❱  5 from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (   │
│    6 │   PromptInputBarCompletionMixin,                                      │
│    7 )                                                                       │
│    8                                                                         │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel.py:22 in <module>             │
│                                                                              │
│    19 │   cursor_readout_position,                                           │
│    20 │   format_cursor_readout,                                             │
│    21 )                                                                      │
│ ❱  22 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content i │
│    23 │   build_completion_panel_content,                                    │
│    24 )                                                                      │
│    25 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│                                                                              │
│ ╭──────────────────────────── locals ────────────────────────────╮           │
│ │   annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │           │
│ │ TYPE_CHECKING = False                                          │           │
│ ╰────────────────────────────────────────────────────────────────╯           │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_content.py:12 in <module>     │
│                                                                              │
│     9                                                                        │
│    10 from sase.ace.tui.agent_completion import AgentCompletionCandidate     │
│    11 from sase.ace.tui.models.tribe_display import named_tribe_identity_col │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds imp │
│    13 │   CompletionPanelKinds,                                              │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12 in <module>       │
│                                                                              │
│     9                                                                        │
│    10 from dataclasses import dataclass                                      │
│    11                                                                        │
│ ❱  12 from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (   │
│    13 │   is_agent_completion_candidate,                                     │
│    14 )                                                                      │
│    15 from sase.ace.tui.widgets.artifact_ref_completion import (             │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_prompt_input_bar_completion_rows.py:7 in <module>               │
│                                                                              │
│    4 original import surface for the completion panel and focused rendering  │
│    5 """                                                                     │
│    6                                                                         │
│ ❱  7 from sase.ace.tui.widgets._history_word_rows import (                   │
│    8 │   append_history_word_completion_row,                                 │
│    9 │   history_word_label_width,                                           │
│   10 )                                                                       │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/ │
│ tui/widgets/_history_word_rows.py:17 in <module>                             │
│                                                                              │
│    14 │   truncate_cell,                                                     │
│    15 )                                                                      │
│    16 from sase.ace.tui.widgets.file_completion import CompletionCandidate   │
│ ❱  17 from sase.ace.tui.widgets.history_word_completion import (             │
│    18 │   HistoryWordCompletionMetadata,                                     │
│    19 │   HistoryWordCompletionPlaceholder,                                  │
│    20 )                                                                      │
│                                                                              │
│ ╭─────────────────────────── locals ───────────────────────────╮             │
│ │ annotations = _Feature((3, 7, 0, 'beta', 1), None, 16777216) │             │
│ │        math = <module 'math' (built-in)>                     │             │
│ ╰──────────────────────────────────────────────────────────────╯             │
╰──────────────────────────────────────────────────────────────────────────────╯
ImportError: cannot import name 'HistoryWordCompletionMetadata' from 
'sase.ace.tui.widgets.history_word_completion' 
(/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui
/widgets/history_word_completion.py)
---------------------------- Captured log teardown -----------------------------
ERROR    asyncio:base_events.py:1875 an error occurred during closing of asynchronous generator <async_generator object App.run_test at 0x7fd3e204ace0>
asyncgen: <async_generator object App.run_test at 0x7fd3e204ace0>
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2137, in run_test
    yield pilot
GeneratorExit

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 1053, in _context
    yield
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2145, in run_test
    raise self._exception
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 654, in _process_messages_loop
    await self._dispatch_message(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 718, in _dispatch_message
    await self.on_event(message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 799, in on_event
    await self._on_message(event)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/message_pump.py", line 820, in _on_message
    await invoke(method, message)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_actions.py", line 254, in _on_resize
    bar = self._find_prompt_bar()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_bar.py", line 37, in _find_prompt_bar
    PromptInputBar = prompt_bar_class()
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_text_area_bar.py", line 22, in prompt_bar_class
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/prompt_input_bar.py", line 18, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
        PromptInputBarCompletionMixin,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion.py", line 5, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
        PromptInputBarCompletionMixin,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py", line 22, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
        build_completion_panel_content,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py", line 12, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
        CompletionPanelKinds,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py", line 12, in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
        is_agent_completion_candidate,
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py", line 7, in <module>
    from sase.ace.tui.widgets._history_word_rows import (
    ...<2 lines>...
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/_history_word_rows.py", line 17, in <module>
    from sase.ace.tui.widgets.history_word_completion import (
    ...<2 lines>...
    )
ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 2132, in run_test
    with app._context():
         ~~~~~~~~~~~~^^
  File "/home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 162, in __exit__
    self.gen.throw(value)
    ~~~~~~~~~~~~~~^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/textual/app.py", line 1055, in _context
    active_message_pump.reset(message_pump_reset_token)
    ~~~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^
ValueError: <Token var=<ContextVar name='active_message_pump' at 0x7fd403dfc7c0> at 0x7fd3e1955280> was created in a different Context
_________ test_edit_and_relaunch_skips_save_for_non_launchable_project _________
[gw7] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fdaa76aa190>

    def test_edit_and_relaunch_skips_save_for_non_launchable_project(
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        """A stale project_file in edit-and-relaunch must not be persisted."""
        monkeypatch.setattr(
            "sase.ace.tui.modals.project_discovery.is_launchable_project",
            lambda _name, projects_dir=None: False,
        )
        saved = _patch_save_recorder(monkeypatch)
    
        class _AppEdit(_App):
            def __init__(self) -> None:
                super().__init__()
                self.mounted: list[Any] = []
    
            def _unmount_prompt_bar(self) -> None:
                return None
    
            def mount(self, widget: Any) -> None:
                self.mounted.append(widget)
    
        app = _AppEdit()
    
>       app._edit_and_relaunch_agent(
            raw_prompt="Do work",
            project_file="/tmp/project/project.sase",
            cl_name="branch",
            is_project_agent=False,
        )

tests/ace/tui/test_entry_points_vcs_prefix_persistence.py:138: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/agent_workflow/_entry_relaunch.py:319: in _edit_and_relaunch_agent
    self._mount_edit_relaunch_prompt_bar(
src/sase/ace/tui/actions/agent_workflow/_entry_relaunch.py:368: in _mount_edit_relaunch_prompt_bar
    from ...widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
__________ test_ctrl_space_dispatches_repeat_agent_from_every_subtab ___________
[gw3] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/bin/python

    async def test_ctrl_space_dispatches_repeat_agent_from_every_subtab() -> None:
        async with AcePage(initial_tab="patches") as page:
            view = page.query_one_widget("#artifacts-view", ArtifactsView)
            calls: list[str] = []
    
            def record_repeat_agent() -> None:
                calls.append(page.app.current_artifacts_subtab)
    
            page.app.action_start_agent_from_patch = record_repeat_agent  # type: ignore[method-assign]
    
            expected = ("stitches", "patches", "beads", "files")
            for index, subtab in enumerate(expected, start=1):
                await page.press(_digit_for(view, subtab))
                await page.expect_state("artifacts_subtab", subtab)
>               assert page.app.check_action("start_agent_from_patch", ()) is True
                       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/test_artifacts_scaffold.py:179: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/app.py:348: in check_action
    return check_app_action(self, action, parameters, super().check_action)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/_app_action_availability.py:94: in check_app_action
    bool(getattr(app, "_screen_stack", ())) and app._prompt_input_active()
                                                ^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/actions/_event_base.py:98: in _prompt_input_active
    from ..widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

    """Score meter, reason chip, and row rendering for smart-ranked history words."""
    
    from __future__ import annotations
    
    import math
    
    from rich.cells import cell_len
    from rich.text import Text
    
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_simple import (
        append_prompt_word_completion_row,
    )
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows_utils import (
        truncate_cell,
    )
    from sase.ace.tui.widgets.file_completion import CompletionCandidate
>   from sase.ace.tui.widgets.history_word_completion import (
        HistoryWordCompletionMetadata,
        HistoryWordCompletionPlaceholder,
    )
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)

src/sase/ace/tui/widgets/_history_word_rows.py:17: ImportError
=============================== warnings summary ===============================
tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
tests/test_prompt_artifact_staging.py::test_concurrent_staging_keeps_manifest_well_formed
  /home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:70: DeprecationWarning: This process (pid=98037) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_fails_before_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_fails_before_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16' to '<deleted>'; restored it.
    next(it)

tests/test_sdd_git_contention.py::test_epic_plan_launch_lock_blocks_other_process_for_same_canonical_anchor
tests/test_sdd_git_contention.py::test_epic_plan_launch_lock_does_not_serialize_distinct_anchors
tests/test_sdd_git_contention.py::test_epic_plan_launch_lock_expiry_can_defer_or_raise_with_holder_details
tests/test_sdd_git_contention.py::test_epic_launch_preflight_defers_without_materializing_under_contention
  /home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:70: DeprecationWarning: This process (pid=97958) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/xprompt/workflow_runner.py:468: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/xprompt/workflow_runner.py:296: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/xprompt/workflow_runner.py:296: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/logs/test_run_log.py::TestLogAgentRun::test_two_process_appends_are_complete_json_records
tests/logs/test_run_log.py::TestLogAgentRun::test_two_process_appends_are_complete_json_records
  /home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:70: DeprecationWarning: This process (pid=97894) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=98037) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/actions/update_toast.py:86: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/actions/agents_sync.py:80: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic agents-sync checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/agents_sync/test_publication_outbox.py::test_two_processes_enqueue_without_lost_or_duplicate_requests
tests/agents_sync/test_publication_outbox.py::test_two_processes_enqueue_without_lost_or_duplicate_requests
  /home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/multiprocessing/popen_fork.py:70: DeprecationWarning: This process (pid=97907) is multi-threaded, use of fork() may lead to deadlocks in the child.
    self.pid = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 25 poisoning change(s) across 25 test(s); 30011 warming mutation(s) filtered; 1409 cooling mutation(s) filtered; 1064 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/.pytest_cache/sase-global-leaks.json -
---------------- sase global leak detector blocking gate failed ----------------
============================= slowest 20 durations =============================
29.35s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
16.94s call     tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py::test_comprehensive_confirmation_honors_disabled_commit_previews
16.81s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
16.26s call     tests/ace/tui/test_plugins_browser_pane_agent_clis.py::test_agent_cli_update_plan_confirm_and_tracked_execution
16.02s call     tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py::test_provider_only_comprehensive_confirmation_explains_no_ranges
15.98s call     tests/ace/tui/test_plugins_browser_pane_comprehensive_update_confirmation.py::test_config_center_handoff_confirms_only_captured_live_provider
14.59s setup    tests/test_agent_artifact_marker_mutation_audit.py::test_tracked_marker_mutation_sites_are_reviewed
14.20s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
9.68s call     tests/test_check_feature_flags_tool.py::test_main_static_on_repo_exits_zero
9.58s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
9.40s call     tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
9.06s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_raises_and_restores_the_claim_when_the_supervisor_never_acknowledges
8.99s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
8.82s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_releases_a_fresh_numbered_claim_when_the_supervisor_never_acknowledges
8.73s call     tests/test_timezone_display_guard.py::test_no_system_clock_display_sites
8.17s call     tests/ace/tui/test_agents_zoom_panel_search.py::test_zoom_search_structural_key_exits_and_then_pages_file
7.42s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
6.60s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
6.04s call     tests/test_keymaps_e2e.py::test_agents_prompt_input_ctrl_k_keeps_local_history_priority
5.99s call     tests/test_procs_supervisor.py::test_process_group_kill_reaps_grandchildren_and_resistant_children
=========================== short test summary info ============================
FAILED tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_commit_repeat_q_and_passthrough - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_yank_and_frozen_refresh - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_exits_when_identity_changes - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/test_agent_metadata_search.py::test_inline_metadata_search_reverse_key_override - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_splits_with_structural_prefix[direct] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_splits_with_structural_prefix[wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_splits_with_structural_prefix[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_splits_with_structural_prefix[nested-wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_splits_with_structural_prefix[plain] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_selection_uses_cursor_row - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_marker_selection_uses_replacement_path - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_exits_populated_bullet_at_content_column[top-level] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_exits_populated_bullet_at_content_column[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_populated_exit_is_one_undo_checkpoint - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_populated_lone_bullet_opens_sibling - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_populated_exit_requires_exact_content_column[before-content-column] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_populated_exit_requires_exact_content_column[inside-content] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_populated_selection_uses_replacement_path - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_twice_exits_bullet_and_undoes_separately[top-level] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_twice_exits_bullet_and_undoes_separately[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_opens_sibling[lone] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_opens_sibling[blank-line-above] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_opens_sibling[nested-lone] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_opens_sibling[cursor-inside-marker] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_twice_exits_from_lone_marker[lone] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_twice_exits_from_lone_marker[blank-line-above] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_undoes_separately - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_llm_provider_usage_limit_disable.py::TestHandlePossibleUsageLimit::test_agy_captured_failure_disables_small_pool_member - StopIteration
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_ctrl_j_prefix_is_its_own_undo_checkpoint - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_tab_indents_and_shift_tab_dedents_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_tab_indents_bullet_from_content[inside-content] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_tab_indents_bullet_from_content[end-of-content] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_tab_indents_bullet_from_content[later-row-inside-content] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_repeated_tabs_accumulate_bullet_indent - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_shift_tab_dedents_one_unit - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_shift_tab_dedents_bullet_from_content[inside-content] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_shift_tab_dedents_bullet_from_content[end-of-content] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_shift_tab_dedents_bullet_from_content[partial-indent-end] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_shift_tab_noop[unindented-bullet] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_shift_tab_noop[prose] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_tab_does_not_indent_active_selection - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_tab_indent_is_one_undo_checkpoint - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_tab_advances_queued_tabstop_before_bullet_indent - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_shift_tab_retreats_queued_tabstop_before_bullet_dedent - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_tab_final_tabstop_falls_back_to_bullet_indent - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_shift_tab_first_tabstop_falls_back_and_remaps_session - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_insert_tab_unknown_trigger_falls_back_to_bullet_indent - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_insert_editing.py::test_prompt_bullet_indent_remaps_insert_dot_capture - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_o_inserts_structural_prefix[direct] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_o_inserts_structural_prefix[wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_o_inserts_structural_prefix[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_o_inserts_structural_prefix[nested-wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_o_inserts_structural_prefix[plain] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_upper_o_inserts_structural_prefix[direct] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_upper_o_inserts_structural_prefix[wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_upper_o_inserts_structural_prefix[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_upper_o_inserts_structural_prefix[nested-wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_normal_upper_o_inserts_structural_prefix[plain] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_bullet_o_undo_keeps_existing_insert_checkpoints - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_bullet_upper_o_undo_keeps_structural_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_bullet_o_dot_repeat_rechecks_destination_context - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_bullet_upper_o_dot_repeat_does_not_leak_marker_to_prose - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_bullet_open_line_editing.py::test_prompt_bullet_upper_o_dot_repeat_avoids_duplicate_nested_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_glossary_navigation.py::test_k_on_glossary_term_pushes_glossary_preview_card - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_glossary_navigation.py::test_k_on_glossary_alias_discloses_matched_text_in_title - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_glossary_navigation.py::test_k_on_wrapped_glossary_continuation_previews_full_term - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_glossary_navigation.py::test_k_on_cold_glossary_defers_without_word_lookup - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_glossary_navigation.py::test_ctrl_bracket_on_glossary_term_opens_definition - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_glossary_navigation.py::test_ctrl_bracket_on_wrapped_continuation_opens_full_definition - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_glossary_navigation.py::test_ctrl_bracket_on_glossary_term_inside_shorthand_argument - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_glossary_navigation.py::test_ctrl_bracket_on_cold_glossary_defers_without_resolution - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_seeded_misspelling_gets_a_span - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_match_is_case_insensitive - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_empty_misspelled_set_paints_nothing - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_words_inside_inline_code_are_skipped - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_words_inside_fenced_blocks_are_skipped - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_substrings_of_larger_words_are_not_matched - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_cache_invalidates_on_generation_bump - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_cache_invalidates_on_text_change - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_large_buffer_is_skipped - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_misspelling_highlight.py::test_highlight_disabled_paints_nothing - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_ctrl_bracket_on_resolvable_token_pushes_jump_modal - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_ctrl_bracket_on_warm_slash_skill_uses_skill_and_prompt_context - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_ctrl_bracket_on_cold_slash_candidate_defers_without_resolution - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_ctrl_bracket_with_single_action_runs_directly - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_ctrl_bracket_on_image_views_it_inside_suspend_without_editor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_ctrl_bracket_on_image_surfaces_viewer_warning - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_ctrl_bracket_on_plain_text_does_not_resolve - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_ctrl_bracket_resolution_error_toasts_distinct_message - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_counted_ctrl_bracket_does_not_jump - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_jump.py::test_ctrl_bracket_does_not_overwrite_dot_repeat - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_k_on_previewable_token_pushes_preview_modal - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_k_on_warm_slash_skill_uses_skill_and_prompt_context - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_k_on_cold_slash_candidate_warms_without_sync_build - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_k_on_cold_unambiguous_absolute_path_stays_a_file - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_k_on_non_previewable_text_does_not_resolve_or_push_modal - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_k_resolution_error_does_not_push_modal - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_counted_k_is_noop_and_does_not_preview - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_k_on_word_inside_shorthand_argument_runs_word_lookup - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_k_on_punctuation_inside_shorthand_argument_previews_owner - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_preview.py::test_k_does_not_overwrite_dot_repeat - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_k_on_correct_word_pushes_definition_modal - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_k_on_misspelling_digit_applies_suggestion - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_spellcheck_escape_leaves_prompt_untouched - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_k_without_aspell_falls_through_to_definitions - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_k_without_lookup_tools_toasts_without_modal - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_k_on_misspelling_records_word_before_panel_opens - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_spellcheck_escape_leaves_word_squiggled - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_k_on_misspelling_without_suggestions_opens_panel_instead_of_notifying - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_spellcheck_accept_clears_the_squiggle - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_spellcheck_dictionary_key_dismisses_panel_without_applying - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_spellcheck_dictionary_added_clears_squiggle_and_notifies - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_spellcheck_dictionary_error_leaves_word_flagged_and_notifies - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_spellcheck_dictionary_unavailable_notifies_warning_and_leaves_flagged - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_k_on_now_correct_remembered_word_forgets_it - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_unavailable_and_error_verdicts_record_nothing[spelling0] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_unavailable_and_error_verdicts_record_nothing[spelling1] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_k_on_non_word_shows_reworded_warning[hello, world-cursor0] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_normal_mode_word_lookup.py::test_k_on_non_word_shows_reworded_warning[foo_bar-cursor1] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_splits_ordered_item[direct] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_splits_ordered_item[wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_splits_ordered_item[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_splits_ordered_item[nested-wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_splits_ordered_item[after-hyphen-list] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_renumbers_following_ordered_siblings - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_renumbers_across_blank_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_preserves_repeat_style - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_preserves_paren_delimiter - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_cursor_survives_width_change_above - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_shifts_owned_block_on_width_change - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_delist_requires_exact_content_column[inside-marker] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_delist_requires_exact_content_column[inside-content] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_delists_at_content_column[top-level] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_delists_at_content_column[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_delists_at_content_column[trailing-items-start-a-new-list] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_delist_is_one_undo_checkpoint - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_populated_lone_item_opens_sibling - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_opens_sibling[lone] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_opens_sibling[blank-line-above] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_opens_sibling[nested-lone] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_opens_sibling[cursor-inside-marker] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_lone_marker_opens_sibling[paren-delimiter] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_marker_only_line_exits_list[last-item] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_marker_only_line_exits_list[renumbers-items-below-the-hole] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_twice_exits_item_and_undoes_separately[top-level] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_twice_exits_item_and_undoes_separately[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_twice_exits_from_lone_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_undoes_split_and_renumber_together - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_prefix_is_its_own_undo_checkpoint - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_selection_uses_cursor_row - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_marker_selection_uses_replacement_path - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_populated_selection_uses_replacement_path - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_output_is_a_formatter_fixed_point[split] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_output_is_a_formatter_fixed_point[repeat-style] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_output_is_a_formatter_fixed_point[delist] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_output_is_a_formatter_fixed_point[delist-keeps-later-start] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_leaves_non_ordered_rows_alone[hyphen-line] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_leaves_non_ordered_rows_alone[unowned-prose] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_leaves_non_ordered_rows_alone[too-many-digits] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_insert_editing.py::test_prompt_insert_ctrl_j_leaves_non_ordered_rows_alone[tight-marker] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_join.py::test_prompt_join_strips_ordered_marker_on_nonblank_fold - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_join.py::test_prompt_join_keeps_ordered_marker_when_folding_onto_a_blank_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_join.py::test_prompt_join_drops_marker_and_renumbers_the_run - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_join.py::test_prompt_join_renumbers_the_run_across_a_blank_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_join.py::test_prompt_join_strips_marker_with_no_preceding_item_to_renumber - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_join.py::test_prompt_join_with_count_renumbers_once_against_the_final_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_join.py::test_prompt_join_drops_marker_and_renumbers_in_one_undo_checkpoint - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_opens_numbered_ordered_sibling[direct] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_opens_numbered_ordered_sibling[wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_opens_numbered_ordered_sibling[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_opens_numbered_ordered_sibling[nested-wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_opens_numbered_ordered_sibling[paren-delimiter] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_opens_numbered_ordered_sibling[hyphen-untouched] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_opens_numbered_ordered_sibling[plain] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_upper_o_opens_numbered_ordered_sibling[direct] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_upper_o_opens_numbered_ordered_sibling[wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_upper_o_opens_numbered_ordered_sibling[nested] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_upper_o_opens_numbered_ordered_sibling[nested-wrapped] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_upper_o_opens_numbered_ordered_sibling[paren-delimiter] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_upper_o_opens_numbered_ordered_sibling[hyphen-untouched] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_upper_o_opens_numbered_ordered_sibling[plain] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_open_line_renumbers_the_run[below-renumbers-siblings] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_open_line_renumbers_the_run[above-renumbers-siblings] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_open_line_renumbers_the_run[renumbers-across-blank-lines] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_open_line_renumbers_the_run[below-preserves-repeat-style] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_open_line_renumbers_the_run[above-preserves-repeat-style] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_open_line_renumbers_the_run[preserves-paren-delimiter] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_shifts_owned_lines_on_marker_width_growth - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_cursor_survives_narrowing_lines_above_it - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_leaves_a_run_that_is_too_large_unrenumbered - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_o_undo_reverts_insertion_and_renumbering_together - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_upper_o_undo_reverts_insertion_and_renumbering - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_ordered_o_dot_repeat_rechecks_destination_context - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_ordered_upper_o_dot_repeat_does_not_leak_marker_to_prose - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_ordered_upper_o_dot_repeat_avoids_duplicate_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_open_line_output_is_a_formatter_fixed_point[below] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_open_line_output_is_a_formatter_fixed_point[above] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py::test_prompt_normal_open_line_output_is_a_formatter_fixed_point[repeat-style] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_nests_ordered_item[ordered-parent] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_nests_ordered_item[ordered-parent-inside-content] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_nests_ordered_item[hyphen-parent] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_nests_ordered_item[continues-nested-run] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_nests_ordered_item[paren-delimiter] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_nests_ordered_item[repeat-style-preserved] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_moves_owned_block_and_closes_source_gap - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_nests_from_column_zero - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_shift_tab_unnests_ordered_item[into-outer-run] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_shift_tab_unnests_ordered_item[into-outer-run-inside-content] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_shift_tab_unnests_ordered_item[hyphen-parent] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_shift_tab_unnests_ordered_item[trailing-nested-item] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_shift_tab_unnest_moves_owned_block - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_shift_tab_unnest_renumbers_width_from_content - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_renumbers_source_run_across_blank_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_ordered_shift_noop[tab-without-parent] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_ordered_shift_noop[tab-after-prose] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_ordered_shift_noop[shift-tab-outermost] - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_ordered_nest_is_one_undo_checkpoint - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_ordered_unnest_is_one_undo_checkpoint - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_does_not_nest_active_selection - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_insert_tab_advances_queued_tabstop_before_ordered_nest - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_ordered_shift_editing.py::test_prompt_ordered_nest_remaps_insert_dot_capture - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestBasicExpansion::test_trigger_expands_with_cursor_at_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestBasicExpansion::test_cursor_at_end_when_no_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestNoExpansion::test_no_match_returns_false - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestNoExpansion::test_no_word_before_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestNoExpansion::test_cursor_after_space - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTriggerInContext::test_trigger_in_middle_of_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTriggerInContext::test_underscore_in_trigger - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTriggerInContext::test_tab_dispatch_expands_trigger_later_on_bullet_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestMultiLineExpansion::test_cursor_on_second_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestMultiLineIndentation::test_continuation_lines_indented - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestMultiLineIndentation::test_no_indent_at_column_zero - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestMultiLineIndentation::test_indented_with_preceding_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestMultiLineIndentation::test_tabstop_on_indented_continuation - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestMultiLineIndentation::test_advance_tabstop_on_indented_expansion - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestSnippetPriority::test_expand_snippet_takes_priority_over_tabstop - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestNestedSessions::test_nesting_at_a_stop_resumes_outer_session_after_inner_exhausts - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTabstopExpansion::test_dollar_one_places_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTabstopExpansion::test_escaped_dollar_is_literal_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTabstopExpansion::test_advance_to_implicit_end - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTabstopExpansion::test_advance_to_explicit_dollar_zero - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTabstopExpansion::test_multiple_tabstops_in_order - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTabstopExpansion::test_no_advance_without_active_session - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTabstopExpansion::test_advance_with_trailing_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestTabstopExpansion::test_advance_after_typing - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestBackwardTabstopNavigation::test_shift_tab_dispatch_retreats_through_key_handling - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestBackwardTabstopNavigation::test_retreat_lands_at_end_of_typed_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestBackwardTabstopNavigation::test_retreat_crosses_nesting_boundary - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestBackwardTabstopNavigation::test_retreat_at_first_stop_is_a_no_op - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestBackwardTabstopNavigation::test_no_retreat_without_active_session - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_prompt_snippet_expansion.py::TestBackwardTabstopNavigation::test_no_retreat_after_the_session_ends - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_blank_line_below_keeps_cursor_and_normal_mode - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_blank_line_above_tracks_original_content_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_blank_line_below_supports_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_blank_line_above_supports_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_blank_line_above_first_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_blank_line_below_last_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_blank_line_commands_handle_empty_buffer - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_blank_line_insertion_is_single_undo_step - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_dot_repeats_blank_line_command - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_unknown_bracket_continuation_is_noop_and_recovers - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_blank_lines.py::test_bracket_prefix_is_consumed_before_app_bindings - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_case_ops.py::test_gu_inner_word_lowercases_text_object - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_case_ops.py::test_gU_to_line_end_uppercases_range - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_case_ops.py::test_g_tilde_word_toggles_case - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_case_ops.py::test_case_line_forms - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_case_ops.py::test_counted_case_line_form_lowercases_multiple_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_case_ops.py::test_case_operator_is_dot_repeatable - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_cc_changes_current_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_cw_changes_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_c_dollar_changes_to_end_of_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_ce_changes_to_end_of_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_c5j_changes_current_and_five_below - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_C_changes_to_end_of_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_C_at_end_of_line_enters_insert_mode - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_C_multiline_only_affects_current_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_escape_clears_pending_operator - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_operator_cleared_after_execution - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_u_undoes_dw - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_u_undoes_dd - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_u_undoes_cw - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_change.py::test_u_noop_when_nothing_to_undo - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_f_moves_to_char - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_f_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_f_no_match_stays - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_f_accepts_upper_k_as_literal_target - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_F_moves_to_char - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_F_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_models_panel_history.py::test_footer_shows_history_only_for_supported_rows[large-True] - assert (('H' in "[green]ctrl+e[/green]=Effort  [green]ctrl+r[/green]=Limit  [green]p[/green]=Providers\n[green]o[/green]=Override  [gr...Clear  [green]e[/green]=Edit  [green]r[/green]=Reset  [dim]j/k[/dim]=Navigate  [dim]'[/dim]=Jump  [dim]esc[/dim]=Close")) is True
FAILED tests/test_prompt_normal_mode_char_search.py::test_F_no_match_stays - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_models_panel_history.py::test_footer_shows_history_only_for_supported_rows[bucket:research-True] - assert (('H' in "[green]ctrl+e[/green]=Effort  [green]ctrl+r[/green]=Limit  [green]p[/green]=Providers\n[green]l/enter[/green]=Open  [dim]j/k[/dim]=Navigate  [dim]'[/dim]=Jump  [dim]esc[/dim]=Close")) is True
FAILED tests/test_prompt_normal_mode_char_search.py::test_t_moves_before_char - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_t_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_t_no_match_stays - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_T_moves_after_char - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_models_panel_history.py::test_footer_shows_history_for_alias_backed_launch_setting - assert 'History' in "[green]ctrl+e[/green]=Effort  [green]ctrl+r[/green]=Limit  [green]p[/green]=Providers\n[green]o[/green]=Override  [gr...Clear  [green]e[/green]=Edit  [green]r[/green]=Reset  [dim]j/k[/dim]=Navigate  [dim]'[/dim]=Jump  [dim]esc[/dim]=Close"
FAILED tests/test_prompt_normal_mode_char_search.py::test_T_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_T_no_match_stays - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_df_deletes_through_char - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_dt_deletes_up_to_char - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_dt_accepts_upper_k_as_literal_target - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_dF_deletes_backward_through_char - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_dT_deletes_backward_till_char - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_cf_changes_through_char - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_operator_no_match_preserves_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_semicolon_repeats_f - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_semicolon_repeats_F - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_semicolon_repeats_t - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_semicolon_repeats_T - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_semicolon_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_semicolon_no_prior_search - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_comma_reverses_f - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_keymaps_e2e.py::test_default_query_shortcuts_follow_the_context_matrix - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_comma_reverses_F - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_comma_reverses_t - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_comma_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_comma_no_prior_search - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_d_semicolon_deletes_to_next_match - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_c_comma_changes_in_reverse - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_t_moves_before_slash - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_f_moves_onto_slash - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_keymaps_e2e.py::test_custom_app_and_leader_query_remaps_stay_independent - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_dt_deletes_up_to_slash - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_df_deletes_through_slash - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_t_moves_before_question_mark - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_dt_deletes_up_to_question_mark - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_bare_slash_activates_prompt_search - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_char_search.py::test_bare_question_mark_activates_reverse_prompt_search - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dd_deletes_current_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_2dd_deletes_two_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dd_last_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dd_only_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dw_deletes_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_d3w_deletes_three_words - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_d3W_deletes_three_WORDS - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_2dw_with_count_on_operator - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_de_deletes_to_end_of_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_db_deletes_backward_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_d_dollar_deletes_to_end_of_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_d0_deletes_to_start_of_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dj_deletes_current_and_next_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dk_deletes_current_and_above_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dG_deletes_to_end_of_document - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dgg_deletes_to_top_of_document - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dl_deletes_character_at_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_dh_deletes_character_before_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_D_deletes_to_end_of_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_D_at_start_of_line_deletes_entire_line_content - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_D_at_end_of_line_is_noop - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_delete.py::test_d_caret_deletes_to_first_nonwhitespace - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_dw - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_keymaps_e2e.py::test_ctrl_at_dispatches_repeat_agent_binding_not_home_space - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_d3w - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_dd - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_2dd - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_D - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_de - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_count_dot_repeats_multiple_times - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_count_dot_overrides_replace_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_count_dot_overrides_indent_line_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_count_dot_overrides_delete_word_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_keymaps_e2e.py::test_prompt_input_space_is_text_after_home_prompt_opens - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_plain_dot_reuses_recorded_operator_motion_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_count_dot_repeats_insert_text_count_times - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_noop_without_prior_mutation - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_not_overwritten_by_motion - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_cw_inserted_text_and_returns_normal - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_keymaps_e2e.py::test_agents_prompt_input_ctrl_j_keeps_local_newline_priority - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_plain_insert_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_append_to_end_of_line_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_repeats_open_line_below_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_dot.py::test_dot_after_pending_operator_repeats_last_mutation - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_indent.py::test_shift_right_indents_current_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_indent.py::test_counted_shift_right_indents_multiple_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_indent.py::test_shift_left_dedents_up_to_one_unit - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_indent.py::test_shift_right_with_line_motion - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_indent.py::test_shift_right_is_dot_repeatable - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_indent.py::test_indent_operator_with_text_object_indents_touched_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_two_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_strips_leading_whitespace - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_strips_trailing_whitespace - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_on_last_line_is_noop - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_empty_next_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_strips_prompt_bullet_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_strips_indented_prompt_bullet_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_collapses_space_after_prompt_bullet_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_prompt_bullet_marker_only_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_keeps_tight_dash - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_keeps_asterisk_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_keymaps_e2e.py::test_agents_prompt_input_ctrl_k_keeps_local_history_priority - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_strips_ordered_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_keeps_thematic_break - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_onto_blank_line_keeps_prompt_bullet_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_count_strips_each_prompt_bullet_marker - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_with_count_exceeding_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_dot_repeats_join - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_dot_repeats_join_with_prompt_bullet_markers - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_join.py::test_join_does_not_create_background_formatter_state - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_j - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_k - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_j_clamps_at_bottom - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_k_clamps_at_top - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_h - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_l - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_space_moves_right - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_space_moves_right - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_space_clamps_at_end_of_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_delete_space_and_dot_repeat - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_w - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_b - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_e - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_G_without_count_goes_to_last_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_G_with_count_goes_to_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_G_with_count_clamps_to_last - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_gg_without_count_goes_to_first_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_gg_with_count_goes_to_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_gg_with_count_clamps_to_last - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_count_cleared_after_use - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_zero_without_prefix_moves_to_start_of_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_zero_appends_to_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_ctrl_d_scrolls_down_half_page - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_ctrl_u_scrolls_up_half_page - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_ctrl_d_clamps_at_bottom - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_ctrl_u_clamps_at_top - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_motions.py::test_ctrl_d_preserves_column - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_ctrl_a_increments_number_under_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_ctrl_a_targets_next_number_on_same_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_ctrl_a_targets_number_on_later_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_ctrl_a_wraps_to_first_number - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_ctrl_a_noops_without_numbers - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_ctrl_x_decrements_signed_number_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_ctrl_x_can_cross_zero - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_number_commands_preserve_leading_zero_width - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_ctrl_a_count_adds_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_dot_repeats_number_increment - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_dot_repeats_number_increment_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_number.py::test_insert_mode_ctrl_a_keeps_readline_behavior - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_paragraph_motions_jump_to_blank_boundaries - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_counted_paragraph_motion_treats_blank_block_as_one_boundary - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_yank_to_next_paragraph_is_exclusive_of_blank_boundary - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_delete_to_next_paragraph_preserves_boundary_blank_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_delete_to_previous_paragraph_preserves_previous_boundary - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_yip_yanks_inner_paragraph_linewise - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_yap_yanks_paragraph_with_trailing_blank_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_dap_at_last_paragraph_includes_leading_blank_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_dip_on_blank_line_deletes_contiguous_blank_block - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_visual_paragraph_motion_extends_selection - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_vip_selects_whole_paragraph_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_paragraphs.py::test_vap_selects_paragraph_plus_trailing_blanks - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_percent_jumps_from_open_to_matching_close - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_percent_searches_forward_on_current_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_percent_jumps_from_close_to_matching_open - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_percent_matches_across_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_percent_honors_nested_same_type_brackets - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_d_percent_deletes_inclusive_range_to_match - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_y_percent_yanks_without_modifying_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_percent_without_bracket_on_line_is_noop - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_d_percent_without_match_clears_pending_operator - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_percent.py::test_visual_percent_extends_selection_to_match - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_ci_double_quote_changes_inside_quotes - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_da_double_quote_includes_quotes_and_trailing_space - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_da_double_quote_includes_leading_space_at_line_end - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_yi_single_quote_searches_forward_on_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_ci_backtick_changes_inside_backticks - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_di_quote_without_match_is_noop_and_clears_operator - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_ci_parenthesis_uses_innermost_nested_pair - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_da_parenthesis_deletes_innermost_pair - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_yib_uses_parenthesis_alias - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_di_brace_spans_multiple_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_yaB_uses_brace_alias - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_ci_square_brackets - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_quote_bracket_objects.py::test_di_angle_brackets - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_cw_on_nonblank_behaves_like_ce - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_cw_count_behaves_like_ce_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_cw_on_blank_keeps_w_motion_behavior - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_cW_on_nonblank_behaves_like_cE - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_r_replaces_character - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_r_accepts_upper_k_as_literal_replacement - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_r_with_count_replaces_multiple_characters - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_r_noop_when_too_few_characters_remain - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_dot_repeats_r - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_ctrl_r_redoes_undo - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_X_deletes_character_before_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_X_with_count_deletes_before_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_S_changes_current_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_S_with_count_changes_multiple_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_ge_moves_to_previous_word_end - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_ge_with_count_moves_multiple_word_ends - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_gE_moves_to_previous_WORD_end - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_dge_deletes_back_to_previous_word_end - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_dgE_deletes_back_to_previous_WORD_end - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_dge_at_buffer_start_aborts_without_deleting - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_dgE_at_buffer_start_aborts_without_deleting - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_ge_with_huge_count_terminates_at_buffer_start - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_small_commands.py::test_noop_X_preserves_dot_repeat - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ys_counted_word_motion_wraps_words_without_trailing_space - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ys_inner_word_wraps_text_object - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ys_inner_word_accepts_bracket_pair - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_yss_wraps_current_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ys_is_dot_repeatable - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ds_double_quote_removes_surrounding_quotes - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ds_parenthesis_accepts_closing_key - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_dsb_uses_parenthesis_alias - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ds_brace_uses_outer_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ds_custom_same_character_surround - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ds_accepts_upper_k_as_literal_surround_target - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ds_double_quote_doubled_removes_nearest_pair - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_cs_double_quote_doubled_with_count_changes_outer_pair - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ds_custom_doubled_same_character_surround - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_cs_double_quote_doubled_changes_nearest_pair - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ds_without_matching_surround_is_noop - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_ds_is_dot_repeatable - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_cs_double_quote_to_single_quote_changes_surround - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_cs_parenthesis_to_brackets_accepts_closing_keys - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_csb_uses_parenthesis_alias - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_cs_brace_uses_outer_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_cs_custom_same_character_surround - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_cs_without_matching_surround_is_noop - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_surround.py::test_cs_is_dot_repeatable - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_diw_middle_of_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_diw_start_of_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_diw_on_whitespace - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_diw_on_punctuation - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_daw_deletes_word_and_trailing_space - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_daw_deletes_word_and_leading_space_at_end - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_daw_on_first_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_diW_deletes_WORD - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_daW_deletes_WORD_and_trailing_space - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_daW_at_end_includes_leading_space - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_ciw_enters_insert_mode - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_d2iw - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_dot_repeat_daw - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_diw_single_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_text_objects.py::test_daw_single_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_toggle_case.py::test_toggle_lowercase_to_uppercase - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_toggle_case.py::test_toggle_uppercase_to_lowercase - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_toggle_case.py::test_toggle_non_alpha_advances_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_toggle_case.py::test_toggle_at_end_of_line_is_noop - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_toggle_case.py::test_toggle_mid_word - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_toggle_case.py::test_toggle_with_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_toggle_case.py::test_toggle_count_clamps_to_line_end - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_toggle_case.py::test_dot_repeats_toggle_case - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_yw_yanks_without_modifying_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_yiw_yanks_inner_word_and_moves_to_start - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_yf_yanks_through_character_search_match - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_yae_yanks_entire_buffer_linewise - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_yy_yanks_current_line_without_moving_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_Y_yanks_counted_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_p_pastes_charwise_after_cursor_with_count_and_undo - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_P_pastes_charwise_before_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_dot_repeats_charwise_paste - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_p_pastes_linewise_below_cursor_on_first_nonblank - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_P_pastes_linewise_above_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_linewise_paste_count_repeats_lines_in_one_edit - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_delete_writes_charwise_register_for_paste - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_change_writes_charwise_register_for_paste - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_normal_mode_yank_paste.py::test_dd_register_pastes_back_into_empty_buffer - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_vim_cursor_class.py::test_prompt_text_area_seeds_insert_cursor_class_on_mount - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_vim_cursor_class.py::test_prompt_text_area_syncs_cursor_class_for_vim_modes - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_v_enters_charwise_visual_and_escape_returns_normal - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_v_toggles_back_to_normal_mode - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_V_enters_linewise_visual_and_selects_whole_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_charwise_visual_delete_writes_register - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_space_extends_charwise_visual_selection_right - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_charwise_visual_yank_backward_selection - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_visual_text_object_selects_inner_word_for_yank - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_visual_text_object_selects_inner_parentheses_for_yank - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_visual_text_object_selects_a_quote_for_delete - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_visual_change_enters_insert_mode - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_visual_p_replaces_selection_and_stores_replaced_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_visual_toggle_case_updates_selection_and_register - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_o_swaps_visual_anchor_and_cursor - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_linewise_visual_yank - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_linewise_visual_delete - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_linewise_visual_p_preserves_following_line - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_linewise_visual_toggle_case_preserves_line_boundaries - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_charwise_visual_indent_applies_to_selected_lines - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_linewise_visual_dedent - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_visual_lowercase_selection - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_visual_uppercase_selection - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_dot_repeats_charwise_visual_delete_same_size - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_dot_repeats_linewise_visual_delete_same_size - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_dot_repeats_visual_change_inserted_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_prompt_visual_mode.py::test_dot_repeats_visual_indent_same_line_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/widgets/test_agent_list_monitor_rows.py::test_family_container_badge_does_not_alter_status_chip - TypeError: format_agent_option() got an unexpected keyword argument 'parallel_family_counts'
FAILED tests/test_prompt_visual_mode.py::test_dot_repeats_visual_case_same_char_count - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection - RuntimeError: pytest -m contract --collect-only failed (exit 2)
FAILED tests/ace/tui/test_prompt_bar_submit_no_cancel_save.py::test_unmount_after_submit_skips_cancel_save_and_detaches - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/test_prompt_bar_submit_no_cancel_save.py::test_cancel_unmount_still_saves_text_as_cancelled - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/test_prompt_bar_submit_no_cancel_save.py::test_unmount_after_submit_is_noop_when_no_bar_mounted - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/test_prompt_bar_submit_no_cancel_save.py::test_unmount_prompt_bar_propagates_recorded_text - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_ace_testing.py::test_ace_page_group_reuses_page_and_resets_prompt_without_history - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_ace_testing.py::test_ace_page_group_rejects_overlapping_checkouts - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_ace_testing.py::test_ace_page_group_reports_reset_hook_leaks - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_ace_testing.py::test_prompt_page_initial_state - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_ace_testing.py::test_prompt_page_press - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_ace_testing.py::test_prompt_page_insert_mode - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_ace_testing.py::test_prompt_page_ta_access - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/test_ace_testing.py::test_prompt_page_cursor_setter - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/test_entry_points_vcs_prefix_persistence.py::test_edit_and_relaunch_skips_save_for_non_launchable_project - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
FAILED tests/ace/tui/test_artifacts_scaffold.py::test_ctrl_space_dispatches_repeat_agent_from_every_subtab - ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/actions/test_prompt_save_xprompt.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/actions/test_prompt_save_xprompt.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/actions/test_prompt_save_xprompt.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/actions/test_prompt_save_xprompt_git.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/actions/test_prompt_save_xprompt_git.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/actions/test_prompt_save_xprompt_git.py:21: in <module>
    from ._prompt_save_xprompt_helpers import _CommitHarness
tests/ace/tui/actions/_prompt_save_xprompt_helpers.py:13: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/actions/test_prompt_save_xprompt_targets.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/actions/test_prompt_save_xprompt_targets.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/actions/test_prompt_save_xprompt_targets.py:27: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/actions/test_prompt_stash_handler.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/actions/test_prompt_stash_handler.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/actions/test_prompt_stash_handler.py:30: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/actions/test_prompt_stash_pump_nonblocking.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/actions/test_prompt_stash_pump_nonblocking.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/actions/test_prompt_stash_pump_nonblocking.py:12: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/actions/test_prompt_stash_restore_open.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/actions/test_prompt_stash_restore_open.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/actions/test_prompt_stash_restore_open.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/actions/test_prompt_stash_update.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/actions/test_prompt_stash_update.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/actions/test_prompt_stash_update.py:16: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_admin_center_selection_resume.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_admin_center_selection_resume.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_admin_center_selection_resume.py:44: in <module>
    from tests.ace.tui.test_xprompt_browser_load_keymap import _md_xprompt
tests/ace/tui/test_xprompt_browser_load_keymap.py:30: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_agent_bulk_kill_edit.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_agent_bulk_kill_edit.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_agent_bulk_kill_edit.py:28: in <module>
    from sase.ace.tui.widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_entry_points_vcs_prefix_editor_reload.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_entry_points_vcs_prefix_editor_reload.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_entry_points_vcs_prefix_editor_reload.py:5: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_event_handlers_artifact_dirty_flags.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_event_handlers_artifact_dirty_flags.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_event_handlers_artifact_dirty_flags.py:15: in <module>
    from ._event_handlers_dirty_flags_helpers import _FakeApp
tests/ace/tui/_event_handlers_dirty_flags_helpers.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_event_handlers_auto_refresh_dirty_flags.py:16: in <module>
    from ._event_handlers_dirty_flags_helpers import _FakeApp, _make_agent
tests/ace/tui/_event_handlers_dirty_flags_helpers.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_event_handlers_prompt_input_dirty_flags.py:12: in <module>
    from ._event_handlers_dirty_flags_helpers import _FakeApp
tests/ace/tui/_event_handlers_dirty_flags_helpers.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_family_member_relaunch.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_family_member_relaunch.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_family_member_relaunch.py:18: in <module>
    from sase.ace.tui.widgets import PromptInputBar
src/sase/ace/tui/widgets/__init__.py:180: in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
../../../../../../share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/importlib/__init__.py:88: in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_launch_submit_context_release.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_launch_submit_context_release.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_launch_submit_context_release.py:12: in <module>
    from tests.ace.tui._event_handlers_dirty_flags_helpers import _FakeApp as _RefreshApp
tests/ace/tui/_event_handlers_dirty_flags_helpers.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_model_completion_panel_titles.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_model_completion_panel_titles.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_model_completion_panel_titles.py:9: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_prompt_bar_editor_stack.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_prompt_bar_editor_stack.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_prompt_bar_editor_stack.py:23: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_prompt_bar_history_requests.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_prompt_bar_history_requests.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_prompt_bar_history_requests.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_prompt_bar_stack_submit_handlers.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_prompt_bar_stack_submit_handlers.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_prompt_bar_stack_submit_handlers.py:26: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py:26: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_prompt_editor_suspend.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_prompt_editor_suspend.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_prompt_editor_suspend.py:16: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_prompt_input_collection_launch.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_prompt_input_collection_launch.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_prompt_input_collection_launch.py:24: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_relaunch_prompt_virtual_wrap.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_relaunch_prompt_virtual_wrap.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_relaunch_prompt_virtual_wrap.py:8: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_restart_prompt_stash.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_restart_prompt_stash.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_restart_prompt_stash.py:12: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import StashedPromptPane
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_xprompt_browser_jump.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_xprompt_browser_jump.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_xprompt_browser_jump.py:24: in <module>
    from tests.ace.tui.test_xprompt_browser_load_keymap import (
tests/ace/tui/test_xprompt_browser_load_keymap.py:30: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_xprompt_browser_load_keymap.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_xprompt_browser_load_keymap.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_xprompt_browser_load_keymap.py:30: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/test_xprompt_target_surface_audit.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/test_xprompt_target_surface_audit.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/test_xprompt_target_surface_audit.py:13: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py:25: in <module>
    from tests.ace.tui.visual._ace_prompt_png_snapshot_helpers import mount_prompt_bar
tests/ace/tui/visual/_ace_prompt_png_snapshot_helpers.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py:19: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_history_word_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_history_word_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_history_word_completion.py:10: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py:18: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_placeholder_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_placeholder_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_placeholder_completion.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_cursor_readout.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_prompt_cursor_readout.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_prompt_cursor_readout.py:16: in <module>
    from tests.ace.tui.visual._ace_prompt_png_snapshot_helpers import (
tests/ace/tui/visual/_ace_prompt_png_snapshot_helpers.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_prompt_editing.py:16: in <module>
    from tests.ace.tui.visual._ace_prompt_png_snapshot_helpers import (
tests/ace/tui/visual/_ace_prompt_png_snapshot_helpers.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py:17: in <module>
    from tests.ace.tui.visual._ace_prompt_png_snapshot_helpers import (
tests/ace/tui/visual/_ace_prompt_png_snapshot_helpers.py:15: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py:13: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_target_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_prompt_target_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_prompt_target_completion.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_prompt_word_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_prompt_word_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_prompt_word_completion.py:9: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_vcs_project_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_vcs_project_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_vcs_project_completion.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_vcs_ref_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_vcs_ref_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_vcs_ref_completion.py:8: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/visual/test_ace_png_snapshots_vcs_repo_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/visual/test_ace_png_snapshots_vcs_repo_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/visual/test_ace_png_snapshots_vcs_repo_completion.py:8: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_artifact_ref_completion_widget.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_artifact_ref_completion_widget.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_artifact_ref_completion_widget.py:26: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_at_reference_completion_rendering.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_at_reference_completion_rendering.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_at_reference_completion_rendering.py:9: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_auto_xprompt_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_auto_xprompt_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_auto_xprompt_completion.py:13: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_directive_completion_interactions.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_directive_completion_interactions.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_directive_completion_interactions.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_file_completion_module.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_file_completion_module.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_file_completion_module.py:15: in <module>
    from ._completion_helpers import create_entries
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_frontmatter_panel.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_frontmatter_panel.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_frontmatter_panel.py:8: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_frontmatter_panel_properties.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_frontmatter_panel_properties.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_frontmatter_panel_properties.py:6: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_frontmatter_panel_subeditors.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_frontmatter_panel_subeditors.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_frontmatter_panel_subeditors.py:18: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_history_word_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_history_word_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_history_word_completion.py:19: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_history_word_rows.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_history_word_rows.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_history_word_rows.py:8: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_local_xprompt_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_local_xprompt_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_local_xprompt_completion.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_model_completion_rows.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_model_completion_rows.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_model_completion_rows.py:8: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_placeholder_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_placeholder_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_placeholder_completion.py:18: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_alt_syntax_editing.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_alt_syntax_editing.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_alt_syntax_editing.py:16: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_alt_syntax_highlight.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_alt_syntax_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_alt_syntax_highlight.py:9: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_artifact_ref_highlight.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_artifact_ref_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_artifact_ref_highlight.py:21: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_at_prefix_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_at_prefix_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_at_prefix_completion.py:13: in <module>
    from ._completion_helpers import CompletionTestApp, create_entries
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_bar_palette_safety.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_bar_palette_safety.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_bar_palette_safety.py:16: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_bar_xprompt_selector_targeting.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_bar_xprompt_selector_targeting.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_bar_xprompt_selector_targeting.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_bullet_highlight.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_bullet_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_bullet_highlight.py:22: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_codeblock_highlight.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_codeblock_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_codeblock_highlight.py:18: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_completion_height.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_completion_height.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_completion_height.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_escape_cancel.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_escape_cancel.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_escape_cancel.py:7: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_file_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_file_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_file_completion.py:12: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_file_history_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_file_history_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_file_history_completion.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_format.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_format.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_format.py:13: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_g_prefix_hint_entries.py:10: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_g_prefix_hint_lifecycle.py:8: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_g_prefix_hint_routing.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_g_prefix_hint_routing.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_g_prefix_hint_routing.py:7: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_glossary_highlighting.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_glossary_highlighting.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_glossary_highlighting.py:17: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_history_trigger.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_history_trigger.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_history_trigger.py:8: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_input_bar_cursor_readout.py:12: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_input_bar_detach.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_input_bar_detach.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_input_bar_detach.py:7: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_input_bar_initial_panes.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_input_bar_initial_panes.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_input_bar_initial_panes.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stack.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_input_bar_stack.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_input_bar_stack.py:13: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stack_editor.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_input_bar_stack_editor.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_input_bar_stack_editor.py:7: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stack_frontmatter_inputs.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_input_bar_stack_frontmatter_inputs.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_input_bar_stack_frontmatter_inputs.py:6: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stack_xprompt_markdown.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_input_bar_stack_xprompt_markdown.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_input_bar_stack_xprompt_markdown.py:10: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_input_bar_stash_load.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_input_bar_stash_load.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_input_bar_stash_load.py:7: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_jinja.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_jinja.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_jinja.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_jinja_pair_editing.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_jinja_pair_editing.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_jinja_pair_editing.py:13: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_live_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_live_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_live_completion.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_local_xprompt_convert.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_local_xprompt_convert.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_local_xprompt_convert.py:8: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_ordered_highlight.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_ordered_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_ordered_highlight.py:22: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_pair_editing.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_pair_editing.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_pair_editing.py:16: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_path_inventory.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_path_inventory.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_path_inventory.py:18: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_search_highlight.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_search_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_search_highlight.py:10: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_search_interactive.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_search_interactive.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_search_interactive.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_keymaps_add_pane.py:10: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_keymaps_focus.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_keymaps_reorder.py:10: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_keymaps_separator_vim.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_keymaps_separator_vim.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_keymaps_separator_vim.py:10: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_snippet_pane_frame.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_snippet_pane_frame.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_snippet_pane_frame.py:9: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_snippet_pane_lifecycle.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_snippet_pane_lifecycle.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_snippet_pane_lifecycle.py:13: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_snippet_pane_model.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_snippet_pane_model.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_snippet_pane_model.py:7: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_submit_cancel.py:23: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_submit_todo.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_submit_todo.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_submit_todo.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stack_subtitles.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stack_subtitles.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stack_subtitles.py:7: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_star_search.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_star_search.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_star_search.py:8: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stash_capture.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stash_capture.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stash_capture.py:18: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_stash_restore_keymap.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_target_completion_previews.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_target_completion_previews.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_target_completion_previews.py:8: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_labels import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_labels.py:8: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_todo_highlight.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_todo_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_todo_highlight.py:26: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_todo_title.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_todo_title.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_todo_title.py:12: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_vcs_mru_cycling.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_vcs_mru_cycling.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_vcs_mru_cycling.py:21: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_virtual_wrap.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_virtual_wrap.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_virtual_wrap.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_word_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_word_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_word_completion.py:12: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_xprompt_highlight.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_xprompt_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_xprompt_highlight.py:16: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_prompt_yank_highlight.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_prompt_yank_highlight.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_prompt_yank_highlight.py:16: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_recursive_finder_modal.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_recursive_finder_modal.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_recursive_finder_modal.py:17: in <module>
    from ._completion_helpers import CompletionTestApp
tests/ace/tui/widgets/_completion_helpers.py:14: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_snippet_expansion_call_sites.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_snippet_expansion_call_sites.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_snippet_expansion_call_sites.py:7: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_vcs_project_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_vcs_project_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_vcs_project_completion.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_vcs_ref_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_vcs_ref_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_vcs_ref_completion.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_vcs_repo_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_vcs_repo_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_vcs_repo_completion.py:11: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_vim_normal_key_containment.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_vim_normal_key_containment.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_vim_normal_key_containment.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_xprompt_arg_hints.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_xprompt_arg_hints.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_xprompt_arg_hints.py:9: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_xprompt_arg_value_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_xprompt_arg_value_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_xprompt_arg_value_completion.py:17: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_xprompt_completion.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_xprompt_completion.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_xprompt_completion.py:8: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/ace/tui/widgets/test_xprompt_completion_spacer.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/ace/tui/widgets/test_xprompt_completion_spacer.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/ace/tui/widgets/test_xprompt_completion_spacer.py:20: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/test_prompt_visual_mode_surround.py - ImportError while importing test module '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/tests/test_prompt_visual_mode_surround.py'.
Hint: make sure your test modules/packages have valid Python names.
Traceback:
tests/test_prompt_visual_mode_surround.py:9: in <module>
    from sase.ace.tui.widgets.prompt_input_bar import PromptInputBar
src/sase/ace/tui/widgets/prompt_input_bar.py:18: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion.py:5: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel.py:22: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_content import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_content.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_panel_kinds import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_panel_kinds.py:12: in <module>
    from sase.ace.tui.widgets._prompt_input_bar_completion_rows import (
src/sase/ace/tui/widgets/_prompt_input_bar_completion_rows.py:7: in <module>
    from sase.ace.tui.widgets._history_word_rows import (
src/sase/ace/tui/widgets/_history_word_rows.py:17: in <module>
    from sase.ace.tui.widgets.history_word_completion import (
E   ImportError: cannot import name 'HistoryWordCompletionMetadata' from 'sase.ace.tui.widgets.history_word_completion' (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/history_word_completion.py)
ERROR tests/test_llm_provider_usage_limit_disable.py::TestHandlePossibleUsageLimit::test_agy_captured_failure_disables_small_pool_member - AttributeError: 'function' object has no attribute 'cache_clear'
ERROR tests/llm_provider/test_provider_disable_routing.py::test_round_robin_skips_disabled_member_and_restores_priority - AttributeError: 'function' object has no attribute 'cache_clear'
ERROR tests/llm_provider/test_provider_disable_routing.py::test_all_disabled_pool_retains_member_zero_without_cursor_advance - AttributeError: 'function' object has no attribute 'cache_clear'
ERROR tests/llm_provider/test_provider_disable_routing.py::test_ordered_fallback_skips_disabled_member - AttributeError: 'function' object has no attribute 'cache_clear'
ERROR tests/llm_provider/test_provider_disable_routing.py::test_alias_override_pauses_and_resumes - AttributeError: 'function' object has no attribute 'cache_clear'
ERROR tests/llm_provider/test_provider_disable_routing.py::test_default_override_pauses_for_disabled_provider - AttributeError: 'function' object has no attribute 'cache_clear'
ERROR tests/llm_provider/test_provider_disable_routing.py::test_autodetection_skips_disabled_provider - AttributeError: 'function' object has no attribute 'cache_clear'
ERROR tests/llm_provider/test_provider_disable_routing.py::test_provider_routing_statuses_include_disable_and_affected_aliases - AttributeError: 'function' object has no attribute 'cache_clear'
= 602 failed, 29467 passed, 10 skipped, 74 warnings, 129 errors in 678.18s (0:11:18) =
error: recipe `test-cost` failed on line 401 with exit code 1

