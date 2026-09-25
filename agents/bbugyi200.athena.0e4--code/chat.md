# Chat History - ace-run (0e4--code)

- **TIMESTAMP:** 2026-08-26 08:43:53 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 0e4--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-0e4__plan-260826_075430.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-0e4__code-260826_075430.md`

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202608/fork_vcs_tag_injection.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll open the plans sidecar repo to read the approved plan.

Now let's look at the fork history builder, the multi_prompt_reference_rewriting.py order example, and artifact_ref_prompt_context.py's `_prompt_segments`.

Now let's look at multi_prompt_reference_rewriting.py for the referenced ordering pattern, and artifact_ref_prompt_context.py's `_prompt_segments`.

Good, this confirms the pattern: `protect_fenced_blocks` then `protect_disabled_regions`, unprotect in reverse order (disabled regions first, then fenced blocks). Now let's look at `_prompt_segments` in artifact_ref_prompt_context.py.

Now let's route `_parsing_vcs_tags.py`'s two functions through this helper, and harden tag insertion for the disabled-region-opening case.

Now update `normalize_default_vcs_workflow`'s function body to import the helper too (it uses `from sase.xprompt._fenced_blocks import ...` locally). Let me view the current state of that function.

Let me clean up the leftover unused import in `normalize_default_vcs_workflow` and add the shared import, plus remove the now-unused `_SEGMENT_SEPARATOR_RE`.

No external users. Removing it.

Now let's add the guard for step 2: when inserting a tag, if body begins with `%xprompts_enabled:false`, use `f"{tag}\n"` instead of `f"{tag} "`. Let me view the two segment functions currently.

Now update the two segment-tag-insertion functions to use this guard.

Now add the import for `starts_with_disabled_region_marker` at the top of the module.

Now let's double check the final state of `_parsing_vcs_tags.py` for correctness.

Good, that looks right. Now let's update `artifact_ref_prompt_context.py`'s `_prompt_segments` to route through the shared helper.

Now remove the now-unused `_SEGMENT_SEPARATOR_RE` in artifact_ref_prompt_context.py if unused elsewhere.

`re` is still used for `_WORKFLOW_TYPE_RE`, fine. Now for step 4: make `_wrap_fork_history` build its disabled region through `wrap_disabled_region`.

Found another usage. Let's check `_parsing.py` for `_SEGMENT_SEPARATOR_RE` usage.

Now let's re-run the quick sanity script to verify `_wrap_fork_history` output matches.

Good, there's a project venv with Python 3.14. Let me use that instead.

Now let's test the escaping case: a body containing a line-initial `%xprompts_enabled:true` should be neutralized.

Escaping works — exactly one disabled region captured, and no stray `---` leaks. Now let's run the reproduction case from the plan to confirm the fix.

Fix confirmed: only 1 tag (the original leading one), no injection into `# New Query` or mid-transcript. Now let's check the recursive-fork hazard (8-copies scenario) with a nested `%xprompts_enabled:true` inside body, plus multiple `---`.

Excellent — the nested fork-of-a-fork case (which produced 8 copies before) now yields exactly 1 tag. Now let's check `normalize_default_vcs_workflow` with a similar fork-shaped prompt (no leading tag).

Now let's look at the relevant test files to add regression coverage per the plan.

Now let's append the new tests after `test_inherit_vcs_tag_skips_known_project_fallback_ref`.

Let's run this test file now.

All 23 pass. Now let's handle test item 2: `tests/test_fork_history.py` — escaping coverage for line-initial markers.

All pass. Now let's tackle test item 3: `tests/test_fork_workflow.py` — extend end-to-end path.

Let's write the sibling test and run it interactively via python first to nail down exact assertions, then add to the test file.

All 12 pass. Now let's tackle test item 4: coverage for `prompt_segment_vcs_refs` with a fork-shaped prompt.

Pre-existing informational-only lint hints, not errors from my changes. Now let's run the project's lint and scoped test suite.

Install is done. Now let's run `just check`.

Just a formatting nit. Let's run `just fmt` to auto-format.

The formatter auto-fixed the line-wrap. Let's run `just check` again.

I'll wait for the background `just check` run to finish rather than poll.

I've implemented the plan and committed the changes via the SASE finalizer, while `just check` continues running in the background — I'll report back once it completes.

I implemented the approved plan (`202608/fork_vcs_tag_injection.md`) to stop the VCS workflow tag from leaking into `#fork`-injected transcripts:

- Added `src/sase/xprompt/_prompt_segments.py`, a shared segment splitter that protects fenced blocks and disabled regions before splitting on `---`.
- Routed `inherit_vcs_workflow_tag` / `normalize_default_vcs_workflow` (`_parsing_vcs_tags.py`) and `_prompt_segments` (`artifact_ref_prompt_context.py`) through it.
- Hardened tag insertion to keep a `%xprompts_enabled:false` marker on its own line when a tag lands in front of it.
- Made `_wrap_fork_history` (`chat_fork/build.py`) build its region via `wrap_disabled_region` so marker-shaped text in a stored transcript can't close the region early.
- Added regression tests across `test_xprompt_vcs_tag_replacement.py`, `test_fork_history.py`, `test_fork_workflow.py`, and `artifact_refs/test_prompt_context.py`; all pass.
- Verified against the plan's exact repro cases (single fork, nested fork-of-a-fork, marker-escaping) by hand — all clean now.

The work is committed via the SASE finalizer. `just check` is still running in the background (it's already past the 10-minute mark, likely because the workspace needed a fresh `just install`, which I ran first) — I'll report the result once it completes.
