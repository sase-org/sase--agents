# Chat History - ace-run (0ci--code)

- **TIMESTAMP:** 2026-08-24 11:59:03 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 0ci--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-0ci__plan-260824_111941.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-0ci__code-260824_111941.md`

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202608/coder_xprompt_plan_ref.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll open the plans sidecar repo first, since I need to use `/sase_repo` before reading files outside my own workspace checkout.

"plans" is a sidecar repo. Opening it now.

Good, all target files exist. Let me read them.

Now let's look at the section around line 2300-2340 in full.

Confirmed: it returns `"plan:202607/plan.md"` format, so stripping the `PLAN_REFERENCE_PREFIX` is correct. My implementation is right. Now let's create the jinja_filters.py module.

Now let's create the new `jinja_filters.py` module.

Now register it in `_jinja.py`'s `_get_jinja_env()`:

Now register it in `workflow_executor_utils.py`'s `create_jinja_env()`:

Now update `coder.md`:

Now update `docs/xprompt.md`. First the coder handoff paragraph:

Now add the filter documentation subsection after the Template Context table:

Let's look at existing test conventions for plan_refs and xprompt loading/expansion.

Now let's verify actual rendering behavior with the verification commands from the plan.

There's a `markdown_wrap.py` module — that explains the rewrapping. This confirms the pipeline reflows paragraph text at render/print time, so exact line-break positions aren't something my template needs to control precisely. Good — my implementation is correct; the observed output matches the plan's expected verification text exactly.

All verification cases pass. Now let's write the test files, using `process_xprompt_references` directly (which won't apply the CLI-level rewrap, so I need to check what that function returns raw vs wrapped).

Now the coder builtin test:

Now let's run the new tests directly.

All 17 tests pass. Now let's run `just fmt` to rewrap the markdown and docs, then `just check`.

That's `just fmt` (prettier) reformatting my test files — expected, not a concern. Let's check the docs/xprompt.md table formatting too, then run `just check`.

Looks good. Now let's run `just check`.

Confirmed: `Justfile` is untouched by me and the symvision failure is a pre-existing issue from an earlier commit (`bf3206b8f`), unrelated to this plan. That's a stale epic-symbol whitelist entry that should be filed as a task bead per the memory guidance, but let's not let it block verifying my own changes — I'll run the lint/tests scoped to what I touched instead.

All confirmed unaffected, as the plan predicted. Now let's run mypy/ruff specifically to double check lint on my changed files (since `just check`'s lint gates other than symvision already passed above).

The symvision failure is pre-existing (stale `--epic-symbol` whitelist entries in `Justfile` from a prior commit, unrelated to my change). I'll file that as a discovered task bead per project convention.

No duplicate. Let me also sweep the last week per the skill's step 5, and check in-progress epic `sase-su` for a causal link before creating a new task.

This is directly caused by the in-progress `sase-su` epic (phase `sase-su.1` already closed, leaving two now-unnecessary whitelist entries). Per the task-bead workflow, that means recording a `DISCOVERED ISSUE` note on the epic instead of filing a standalone task.

Let me run a broader sweep of xprompt tests directly (bypassing the pre-existing symvision blocker) since `_jinja.py` is imported broadly.

All 2232 relevant tests pass with no regressions. The implementation is complete and verified.

## Summary

Implemented the approved plan (`202608/coder_xprompt_plan_ref.md`) to rewrite the `#coder` xprompt so it names the approved plan instead of inlining it:

- **`src/sase/sdd/plan_refs.py`** — added `plan_reference_display_path()`, returning the `YYYYmm/<name>.md` portion of a plan path/reference, with pass-through-unchanged fallback for anything not provably a plan.
- **`src/sase/xprompt/jinja_filters.py`** (new) — `register_prompt_filters()` registering the `plan_ref_path` Jinja filter.
- **`src/sase/xprompt/_jinja.py`** and **`workflow_executor_utils.py`** — register the filter on both prompt-rendering environments.
- **`src/sase/xprompts/coder.md`** — new body: `The {{ plan_file | plan_ref_path }} plan file has been reviewed and approved. Implement it now.` (no more `@` inlining).
- **`docs/xprompt.md`** — corrected the coder-handoff paragraph (automated hand-off still inlines with `@`; `#coder` now names+reads) and documented the new filter.
- **Tests** — new `tests/test_xprompt_plan_ref_filter.py` and `tests/test_xprompt_coder_builtin.py` (17 tests, all passing).

Verified via the plan's own `sase xprompt expand` commands, plus a full sweep of 2232 xprompt/jinja/workflow-executor tests (all pass, no regressions) and the existing tests the plan called out as unaffected (`test_epic_approval.py`, `test_plan_approval_launch_reliability_integration.py`, `test_workspace_clone_reconciliation.py`).

Two notes:
- `just check`'s symvision gate fails, but for a cause unrelated to this change: two stale `--epic-symbol` whitelist entries in `Justfile` (`sase-su.2(plan_provider_drain)`/`execute_provider_drain`) from the in-progress `sase-su` epic. I confirmed the `Justfile` is untouched by my diff and recorded a `DISCOVERED ISSUE` note on that epic rather than filing a duplicate task.
- The plan's verification section lists `sase xprompt expand '#coder:plan:202608/foo.md'` as a working example, but the xprompt colon-shorthand grammar doesn't support colons inside its argument (pre-existing, unrelated limitation) — the parenthesized form `#coder(plan:202608/foo.md)` is needed instead, which I confirmed renders correctly.

Now I'll build the manifest with a commit decision based on the evidence brief describing the completed work.

The finalizer declaration has been submitted successfully — the commit payload for the `main` repository was accepted, covering the plan-reference xprompt work (`plan_reference_display_path()`, the `plan_ref_path` Jinja filter, `#coder` xprompt update, docs, and tests).
