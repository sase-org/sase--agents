# Chat History - ace-run (dq--plan)

- **TIMESTAMP:** 2026-07-18 14:38:03 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** dq--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-dq__plan-260718_142610.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260718_142610.md`

**Plan:** /home/bryan/.sase/plans/202607/history_word_completion.md


## Prompt

#gh:gh_sase-org__sase We recently added support to the prompt input widget keymap for
completing words that already exist in the prompt input widget when there are no
other available completions. Can you help me start triggering a different
completion menu when this fails, which uses a set of commonly used words?

- These commonly used words should not be static but instead should be derived
  from historical user prompts by saving the last `<N>` >=`<M>` character unique
  words that were used in previous prompts.
- Let's default to 1000 for `<N>` and 5 for `<M>` but make these configurable
  via new sase config field that users can override.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/history_word_completion.md`

> # Plan: History-word fallback completion menu
> ## Product context
> The ACE prompt input recently gained prompt-local word completion: the manual `Ctrl+T` completion chain in
> `FileCompletionOpenMixin._try_file_completion_tab` (`src/sase/ace/tui/widgets/_file_completion_open.py`) ends at
> `_try_prompt_word_completion_tab`, which completes a plain word prefix from words already present in the active pane
> (`src/sase/ace/tui/widgets/prompt_word_completion.py`). When no other pane word matches the prefix,
> `build_prompt_word_completion_result` returns `None`, the menu clears, and the keypress does nothing.
> This plan fills that dead end: when prompt-local word completion fails, `Ctrl+T` opens a **history words** menu whose
> candidates are the last `N` unique words (of at least `M` characters) the user typed in previously recorded prompts.
> Defaults: `N = 1000`, `M = 5`, both user-configurable.

*See full plan file for details.*

