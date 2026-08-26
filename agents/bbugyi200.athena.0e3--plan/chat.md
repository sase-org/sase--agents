# Chat History - ace-run (0e3--plan)

- **TIMESTAMP:** 2026-08-26 07:58:38 EDT
- **MODEL:** claude/opus
- **AGENT:** 0e3--plan

**Plan:** /home/bryan/.sase/plans/202608/case_aware_word_completion.md


## Prompt

#gh:gh_sase-org__sase Can you help me make the common words (i.e. words found in previous prompts) completion in the prompt input widget smart about how casing is handled and case-insensitive? For example, if the user is typing `SPECTAC` and uses the `<ctrl+t>` keymap and the correct and only common words completion is `spectacular`, then we should auto-complete `SPECTACULAR`.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/case_aware_word_completion.md`

> # Plan: Case-smart prompt-history word completion
> ## Goal
> Typing `SPECTAC` and pressing `<ctrl+t>` should insert `SPECTACULAR` when the only
> matching history word is `spectacular`. More generally, the `prompt_word` and
> `history_word` completion menus should:
> 1. infer the casing the user typed and apply it to the completed word, and
> 2. treat case-variant spellings of the same word (`xprompt` / `Xprompt` / `XPROMPT`) as
>    one completion, not three competing rows.
> ## Background: what already works, and what does not
> Matching is **already** case-insensitive, so that part needs no work:

*See full plan file for details.*

