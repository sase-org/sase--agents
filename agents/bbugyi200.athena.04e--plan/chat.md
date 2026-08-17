# Chat History - ace-run (04e--plan)

- **TIMESTAMP:** 2026-08-17 06:01:32 EDT
- **MODEL:** claude/opus
- **AGENT:** 04e--plan

**Plan:** /home/bryan/.sase/plans/202608/placeholder_completion_ranking.md


## Prompt

#gh:gh_sase-org__sase We recently added good sorting, using recency/frequency/relation, of common words in the prompt input widget's completion menu. Can you now help me do something very similar for placeholder tag (e.g. `<foo>`) completion? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/placeholder_completion_ranking.md`

> # Plan: Rank saved placeholder tags by relation, recency, and frequency
> ## Problem
> The `<` menu has two candidate groups. The prompt-local group (cyan `<>` badge) is
> ordered by the document itself and is fine. The saved group (gold `◆` badge) is drawn
> from `~/.sase/prompt_placeholders.json` and is ordered by `_display_order()`
> (`src/sase/history/prompt_placeholders.py`): `count` desc, then `last_used` desc, then
> `text` asc. `build_placeholder_completion_candidates()`
> (`../sase-core/crates/sase_core/src/editor/placeholder.rs`) preserves that caller order
> verbatim after its prefix filter and dedup, so the persisted order _is_ the menu order.
> That lexicographic ordering has the same practical failures the history-word menu had

*See full plan file for details.*

