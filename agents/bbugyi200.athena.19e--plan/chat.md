# Chat History - ace-run (19e--plan)

- **TIMESTAMP:** 2026-11-07 07:08:36 EST
- **MODEL:** claude/opus
- **AGENT:** 19e--plan

**Plan:** /home/bryan/.sase/plans/202611/literal_coder_decisions_block.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/literal_coder_decisions_block.md`

> # Keep the coder Reviewer decisions block literal
> ## Why the 19c agent failed
> `19c--plan` (project `gh_bbugyi200__love`, tag `+love`) proposed a tale with three
> `decisions:`. Two of the `ask` strings named the project by its tag, for example
> `ask: Should the coder also add a one-line pointer to the +love project in ~/bob/love.md?`.
> The reviewer approved in ACE. The host-built `19c--code` prompt then failed after 40s,
> before the provider ran:
> ```
> WorkflowExecutionError: Step 'main' failed: Multiple VCS-tagged workflows in one prompt: #gh, #gh, #gh.
> ```

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase The `19c` sase agent just failed. Is there something that we can/should fix here?
If so, use your /sase_plan skill to plan the appropriate changes. Think hard about this. %m:@xlarge

## Response

Found the failure: the 19c successor (code step) died with "Multiple VCS-tagged workflows in one prompt: #gh, #gh, #gh". Now digging into where those three `#gh` tags came from.

The user already worked around it by launching 19d by hand. I'm now reading the macro/project-tag memory and expansion code to decide where the fix belongs.

The `+love` scan and the decisions block renderer both live in Rust core. I'm opening the sase-core repo to see how literal zones are handled there.

Good news so far: inline code already counts as a literal zone for launch parsing. Next I'm reading the Rust prompt-block renderer to see exactly how it quotes `Context:` text.

There's a ready precedent. `wrap_disabled_region` already makes data inert in host-built prompts: chat-fork transcripts and retry prompts use it. Let me look at those usages.

All expansion call sites go through the zone-aware Rust scanner. I'll test it directly against the real project catalog: does `+love` stay unexpanded inside a disabled region?

I have enough to plan. Root cause: the host builds the coder prompt by pasting the planner's decision `ask` text in raw, and project-tag/macro expansion runs over all of it. Writing the plan now.

Tale-sized, small. I'm finding an existing test harness for the successor prompt so the plan can name a concrete end-to-end regression test.

Validation wants a toggle with shorter `ask` and `why` text. Fixing those.

Plan validates cleanly. Proposing it.

Yes, there's a real bug worth fixing. I've written a plan for it and proposed it. It's staged for your review in ACE.

## Why 19c failed

`19c--plan` worked fine. The agent that failed was its coder successor, `19c--code`. It died after 40 seconds, before the model ever ran, with:

```
Multiple VCS-tagged workflows in one prompt: #gh, #gh, #gh.
```

Two of the planner's decision questions mentioned the project by its tag, e.g. *"Should the coder also add a one-line pointer to the `+love` project in ~/bob/love.md?"*.

When you approved the plan, the host built the coder's prompt and pasted each question in as `Context: "..."`. The Rust function that does the quoting, `quoted()` in sase-core's `sheet.rs`, only removes newlines and escapes quote marks. So prompt expansion still treated the pasted text as live syntax:

- Both `+love` mentions were rewritten to `#gh:gh_bbugyi200__love`.
- Together with the prompt's real `#gh` line, that made three, so launch refused the prompt.

The failure is deterministic: retrying `19c--code` will fail the same way. Your manual `19d` launch already covers the work. More broadly, any decision question that mentions a project tag, a `#macro`, a `%directive` or an `@file` will either break the coder launch or quietly change it. For example, `%model:x` in a question would switch the coder's model.

## The proposed fix

The plan is a small, single-agent change (`sase_plan_literal_coder_decisions_block.md`):

1. **Main fix:** wrap the "Reviewer decisions" block in a disabled region (`%macros_enabled:false … :true`) using the existing `wrap_disabled_region` helper. The change goes in `_reviewer_decisions_block` in `src/sase/axe/run_agent_exec_plan_accept.py`.
   - Every other host-built prompt that embeds data already does this: gate and monitor follow-ups, fork history, and QA prompts.
   - Every expansion step skips these regions, and the markers are removed before the model sees the prompt.
   - I tested this against your real project list: unwrapped, `+love` gets rewritten; wrapped, it's left alone.
   - The reviewer's "Additional instructions" stay outside the wrapper, so macros there still work.
2. **Why not a simpler fix:**
   - Backticks don't help, because the step that raised this error ignores inline code.
   - Changing it in sase-core would also add the markers to `sase bead read` output. So there's no sase-core change and no version-pin bump.
3. **Tests:** a regression test with questions containing a project tag, a second `#gh:` ref, `%model:` and `@path`. It checks that nothing gets expanded, that only one VCS workflow is found, and that the model still sees the text unchanged. One existing test that checks the block's exact opening text needs updating.
4. **Your call (one decision, default yes):** make the error name each full ref and explain that project tags turn into VCS refs. `#gh, #gh, #gh` hid the cause here, and a prompt that names two projects hits the same error.
5. **Docs:** one sentence in `docs/reference/work-units/plan-format.md` saying decision text reaches the coder literally.

I kept that plan's own decision question free of any expandable syntax, so its coder can't hit this same bug before the fix lands. Nothing was committed this turn, since only the plan was produced.
