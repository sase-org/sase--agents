# Chat History - ace-run (03s.w0--plan)

- **TIMESTAMP:** 2026-08-16 12:13:21 EDT
- **MODEL:** claude/opus
- **AGENT:** 03s.w0--plan

**Plan:** /home/bryan/.sase/plans/202608/word_completion_ranking.md


## Prompt

#gh:gh_sase-org__sase We currently support completion for common words used in previous prompts via
the `<ctrl+t>` keymap, but that completion menu often doesn't sort its entries ideally.
Can you help me fix this by sortin common words by recency/frequency/relation with other
words in the prompt (in other words, words that were used in prompts containing other
words that already exist in the current prompt input widget should be prioritized)?

- Think hard about the smartest way to do this and make sure we prioritize recency /
  frequency / relation appropriately.
- Add some (visually appealing) signal as to why each word is prioritized the way it is
  in the completion menu where possible (without hurting performance).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! 

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus %w:03s

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/word_completion_ranking.md`

> # Plan: Rank Ctrl+T history words by relation, recency, and frequency
> ## Problem
> `Ctrl+T` falls back to prompt-history words (`history_word` menu) once prompt-local
> words have no match. Today `collect_recent_prompt_words()`
> (`src/sase/history/prompt_words.py`) walks every shard newest-first and returns the
> first `history_word_count` distinct spellings it sees, and
> `build_history_word_completion_result()`
> (`src/sase/ace/tui/widgets/history_word_completion.py`) preserves exactly that order
> after a case-insensitive prefix filter. So the menu is ordered purely by "most recently
> written", which has three practical failures:

*See full plan file for details.*

