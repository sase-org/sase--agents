# Chat History - ace-run (6k--plan)

- **TIMESTAMP:** 2026-07-12 09:02:49 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 6k--plan

**Plan:** /home/bryan/.sase/plans/202607/prompt_stash_preview_pane.md


## Prompt

#gh:gh_sase-org__sase Can you help me give the prompt stash panel in the TUI a nice pane on the right that previews the currently selected prompt? This pane should have good syntax highlighting that supports markdown elements and native xprompt elements (e.g. xprompt invokations like `#foo` and directives like `%wait`).

I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/prompt_stash_preview_pane.md`

> # Plan: Prompt Stash Preview Pane with XPrompt + Markdown Syntax Highlighting
> ## Product Context
> The prompt stash picker (`StashedPromptsModal`, opened via `@` / `Ctrl+G p` / empty `Ctrl+S`) currently shows each
> stashed prompt as a single truncated line — a 36-character first-line snippet next to age, project, and bundle chips. To
> decide which prompt to restore (or which pinned row to overwrite), users must recognize a prompt from its first ~36
> characters. That fails for prompts that start with a directive line, share a common prefix, or are multi-prompt bundles.
> This plan adds a **preview pane on the right side of the stash picker** that renders the full text of the highlighted
> entry with rich syntax highlighting:
> - **Markdown elements** — headings, emphasis, lists, links, code fences — via the markdown lexer.
> - **Native xprompt elements** — invocations (`#foo`, `#!foo`, `#foo(a, b)`, `#foo:arg`, `#foo+`), directives (`%wait`,

*See full plan file for details.*

