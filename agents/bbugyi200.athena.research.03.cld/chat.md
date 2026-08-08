# Chat History - ace-run (research.03.cld)

- **TIMESTAMP:** 2026-08-08 11:52:00 EDT
- **MODEL:** claude/opus
- **AGENT:** research.03.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260808_113853.md`

## Prompt

%id(cld, clan=research.03) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I wanted to find a reliable way to invoke xprompts by tag
instead of by name. Can you do some research to help me decide the best way to implement
this? Make sure you audit this codebase for existing xprompt tags and understand their
purpose/usage before diving too deep into your research. End your analysis with a
recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by auditing the codebase for existing xprompt tag infrastructure before researching invocation designs.

I have the full picture. Writing the report now.

Research written to `sase/repos/research/202608/xprompt_tag_invocation.md`.

## What the audit found

sase **already has tag-based invocation** — `src/sase/xprompt/tags.py`. It's the binding mechanism for 11 core behaviors (bead automation, mentor review, fix-hook, rollover, VCS wrapping). It's just not user-invocable, and it isn't reliable. Live census: **15 of 106 prompts carry a tag**, across a closed 15-member enum, and 3 members (`crs`, `append_to_pr`, `create_epic_bead`) have zero holders on this machine while two of them still have live consumers silently receiving `None`.

The one enum does three incompatible jobs: set markers (`vcs`, `rollover` — 7 prompts hold `rollover`), tolerant role bindings (`get_by_tag`), and strict role bindings (`get_by_tag_strict`). Only the role categories can be invoked; nothing declares which is which.

Five verified defects, two of which matter most:

- **An unknown tag crashes the whole catalog.** `parse_tags` raises, `load_xprompt_from_file` doesn't guard, and the exception escapes `get_all_xprompts()`. Reproduced. Every other load failure in that package is a non-fatal `record_load_issue`; tags are the sole exception. Meanwhile the TUI frontmatter panel treats the *same YAML key* as free-form `list[str]`, so saving an xprompt with `tags: research` from the TUI writes a file that bricks the next load.
- **"Highest priority wins" is a dict-ordering artifact that provably inverts.** `get_by_tag` returns `matches[-1]`, but `dict.update` doesn't reorder existing keys, and `get_all_prompts` returns `{**xprompts, **workflows}` — so *every* xprompt sorts before *every* workflow. A user's `~/sase/xprompts/my_propose.md` with `tags: propose` loses to the built-in `propose.yml`, which is exactly the override story `src/sase/bead/xprompts.py:5-7` documents as working. The existing test patches a hand-ordered dict, so CI can't see it.

## Recommendation

Not "add a tag syntax" — that's the cheap part. Three phases:

1. **Deterministic resolver.** Rank by `XpromptSource.priority` (already Rust-owned via `content_layout`), key `(source_rank, kind_rank, name)`, declared `ROLE` vs `MARKER` cardinality, ambiguity → reproducible winner + `doctor` issue instead of `get_by_tag_strict`'s raise, plus a config `xprompt_tag_bindings` pin as the escape hatch.
2. **Open the vocabulary; stop raising.** Unknown tags become opaque strings + load issues. This is what unifies the TUI's free-form tags with core's roles and is the precondition for user-authored roles.
3. **Reserved `tag/` namespace** — `#tag/propose`, `#!tag/land_epic` — materialized as synthetic catalog entries. Zero lexer changes (`ns/name` already parses), direct precedent in `memory/` and `skills/`, and args/shorthand/`#!`/completion/`xprompt show` all fall out free.

I rejected a new sigil (`#@propose`) — the reference grammar is duplicated in two places and `@` is already overloaded — and rejected textual rewriting in `resolve_xprompt_aliases`, which runs before fence protection and would rewrite inside code blocks.

One thing worth your call: the D1 crash is a standalone bug independent of whether you adopt tag invocation. Want me to file it as a task bead via `/sase_new_task`, or leave it folded into whatever plan comes out of this?

I made these changes — the research report is mine from this session. Committing now.

Committed and pushed.

- **Repo:** `sase/repos/research` (the linked repo and SDD sidecar entries in the finalizer list resolve to the same checkout, so one commit covers both)
- **Commit:** `3b2e845 docs(research): evaluate tag-based xprompt invocation`
- **File:** `202608/xprompt_tag_invocation.md` (456 lines, new)
- **Verified:** `git status --short --branch` reports `## main...origin/main` with no dirty entries and no ahead/behind — clean and in sync with the remote.

The commit message describes only this report: the audit of the existing `XpromptTag` enum and its consumers, the five verified defects, and the three-phase recommendation.

One item still open from before the finalizer ran, for your call: the unknown-tag crash (`parse_tags` raising out through `get_all_xprompts()`) is a standalone bug independent of whether you adopt tag invocation. Say the word and I'll file it via `/sase_new_task`.
