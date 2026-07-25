# Chat History - ace-run (ht--plan)

- **TIMESTAMP:** 2026-07-22 07:20:47 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** ht--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-ht__plan-260722_070527.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260722_070527.md`

**Plan:** /home/bryan/.sase/plans/202607/prompt_todo_highlighting.md


## Prompt

#gh:gh_sase-org__sase Can you help me start highlighting TODO something really distinct and noticable in the prompt input widget? I want to start leaving TODOs for myself in stashed prompts (which I use when I'm working on a long prompt sometimes) and I need a way to easily spot them when I load the prompt back into the prompt input widget. I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/prompt_todo_highlighting.md`

> # Plan: Beautiful TODO highlighting for prompt drafts
> ## Context and product outcome
> Long prompts are often stashed and restored across writing sessions. ACE currently restores their text faithfully, but
> there is no visual language for unfinished notes; because a restored prompt is focused at its end, an earlier reminder
> can also be outside the viewport. Add a prompt-native TODO annotation treatment that makes visible markers beautiful and
> obvious while a small title chip reports TODOs anywhere in the loaded prompt stack.
> This is presentation-only behavior in `PromptTextArea` and `PromptInputBar`. Stash serialization, restoration ordering,
> prompt text, submission payloads, and external-editor files must remain byte-for-byte unchanged. Consequently, no Rust
> core or prompt-stash format change is needed: every path that constructs or rebuilds a `PromptTextArea`—initial prompt,
> history load, external-editor return, and mounted or fresh-bar stash restore—should acquire the behavior automatically.

*See full plan file for details.*

