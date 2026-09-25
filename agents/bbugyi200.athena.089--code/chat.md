# Chat History - ace-run (089--code)

- **TIMESTAMP:** 2026-08-19 18:24:01 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 089--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-089__plan-260819_164634.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-089__code-260819_164634.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase @sase/repos/plans/202608/alias_pool_fallbacks.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by reading the approved plan and the implementation skill so the work follows the documented approach.

This is a tale-sized implementation, not a PR-plan DAG. I'll load the current selector stack and start implementing the last-resort grammar.

Next I’ll read resolution, ACE surfaces, doctor, and the existing tests so the new grammar slots into the current flow.

I have the current selector stack. Next I’ll add the parenthesized last-resort grammar and thread it through resolution, doctor, ACE, and the shipped `@large` default.

Parser and selector index are in place. Next I’ll wire resolution so pool and last-resort members share one selection path.

ACE surfaces are updated. Next I’ll correct the docs, schema, and default-config grammar comments.

Docs are updated. Next I’ll add the parser, selection, doctor, and ACE tests the plan requires.

A few tests still patch the old resolution-module selector. I’ll check those call sites and retarget them.

Install finished. I’ll run the focused selector, doctor, and Models-panel tests next.

Formatting is done. I’ll inspect the generated `@large` docs row and the reformatted files next.

Symvision flagged the old selection helpers as unused. I’ll read the unused-symbol rules and keep those primitives public as the plan requires.

I'll re-export the selection primitives from resolution so they stay public and Symvision still sees a production consumer.

The scoped run escalated to the full suite. I’ll rerun the five failures to separate flakes from real regressions.

Several Models-panel goldens shifted by the same pixel count. I’ll inspect a diff to see whether that’s the new `@large` string or unrelated drift.

Last-resort tails for model-alias pools are in. A parenthesized `|` pool can now take an ordered `||` fallback (`(A | B) || C`), and shipped `@large` uses that form.

**Selection.** `@large` is now:

```text
(claude/opus@xhigh | codex/gpt-5.6-sol@xhigh) || grok/grok-4.6@xhigh
```

Claude and Codex still round-robin when either CLI is installed and not hard-disabled. Grok is chosen only when **every** pool member is unavailable. An all-soft pool still rotates among itself. Diverting to the tail does not read or advance `~/.sase/llm_lb.json`. The pool fingerprint is unchanged, so existing `@large` cursors survive.

Unparenthesized `A | B || C` is still rejected. `(A | B)` is grouping only and normalizes to `A | B`.

**Surfaces.** Doctor, Launch Control, and the guided builder understand the new expression: the pool chip stays `pool 2/2` (Grok does not inflate it), descriptions insert a `fallback:` separator, and the builder has `f=fallback`. Toggle refuses to flatten a tail into `A || B || C`. Docs, schema, and the `default_config.yml` example were updated; `just fmt-docs` regenerated the `@large` table row.

**Verification.** Lint is green. Focused selector/doctor/ACE tests passed. `just check` escalated to the full suite because `model_alias_defaults.yml` is a data asset: 34,762 passed. Five failures reran green on the same tree:

- Occupancy: corroborated existing flake **sase-r4**
- Leak-detector snapshot: noted on epic **sase-j7**
- Snippet-name verdict race: filed **sase-r7** (ready)

`sase doctor -C config.model_aliases` parses the new `@large` expression and does not claim Grok is the current selection when a pool provider is available. Only the selector-builder PNG golden was updated (`f=fallback` in the footer). Other Models-panel goldens that failed in a broader visual run differ only by an unrelated `t=tmux Agent` footer key; those were left alone.

No commit was made.

The implementation is already on disk. I’ll load the commit skill and commit these changes now.

I'll record the commit skill, then inspect status and the diff so the message matches these changes.

The tree matches the last-resort pool work. I’ll write the commit message and create the stitch.

The commit is still running; I’ll wait on it in this turn rather than exiting.

Committed and pushed `feat(llm): add last-resort tails for model-alias pools` (`9ca7fe19c`). Working tree is clean and in sync with `origin/master`.

Parenthesized `|` pools now take an ordered `||` tail: `(A | B) || C` still round-robins A and B, and C is used only when every pool member is unavailable. Unparenthesized `A | B || C` stays rejected. Shipped `@large` is that form, so Claude and Codex keep their existing rotation and cursor; diverting to the tail does not advance `llm_lb.json`. Doctor, Launch Control, and the guided builder describe the tail separately and do not inflate the pool chip.
