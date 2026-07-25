# Chat History - ace-run (77--plan)

- **TIMESTAMP:** 2026-07-12 16:24:33 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 77--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-77__plan-260712_161611.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260712_161611.md`

**Plan:** /home/bryan/.sase/plans/202607/prompt_input_xprompt_highlighting.md


## Prompt

#gh:gh_sase-org__sase Are there any areas in the TUI where we could add better xprompt syntax highlighting support? I think we have pretty good syntax highlighting for this, for example, in the prompt stash panel's preview pane, but I don't think the prompt input widget supports anything like this. Make sure this doesn't hurt performance too much.

I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/prompt_input_xprompt_highlighting.md`

> # Plan: Live xprompt Syntax Highlighting in the Prompt Input Widget
> ## Problem & Motivation
> The `sase ace` TUI has excellent xprompt syntax highlighting in the prompt stash preview pane (`highlight_prompt_text`
> in `src/sase/ace/tui/util/xprompt_syntax.py`): `#xprompt` invocations glow green, `%directives` gold, `%{a | b}` alt
> fan-outs purple, and `---` swarm separators blue — with fenced code blocks and `%xprompts_enabled:false` regions
> correctly left alone.
> The prompt input widget (`PromptTextArea`), where users actually _compose_ these prompts, has none of this. It
> highlights Jinja (`JinjaHighlightMixin`), the `%{...}` alt shorthand (`AltSyntaxHighlightMixin`), and search matches
> (`SearchHighlightMixin`) — but `#gh:sase`, `#pr:my_change`, `%auto`, `%m:opus`, and `---` all render as plain markdown
> text while typing. This is exactly where highlighting has the most value: instant feedback that a marker was recognized

*See full plan file for details.*

