# Chat History - ace-run (research.5s.grk)

- **TIMESTAMP:** 2026-11-21 17:40:18 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** research.5s.grk
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261121_172603.md`

## Prompt

%id(grk, clan=research.5s)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.5s.cdx`, `research.5s.cld`, `research.5s.mus`, `research.5s.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to think of the best possible name for what I now call the "prompt input widget".
This name should be added as a new glossary term that describes the widget, the way the
prompt input widget stacks work, and how the prompt input widget property panel. I want
to keep this new term concise and useful for future agents.

Can you do some research with the goal of helping me think of the best possible name?
End your analysis with a ranked list of names you think I should consider and a
recommended new glossary term entry for your #1 pick. 
First run `sase repo open research -r "Write this research report"` and use the path it prints as `<research checkout>`. Write this research to a new markdown file under `<research checkout>/202611/`.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path under the opened research checkout and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'll research the prompt-input widget independently, starting with the research checkout and the project's glossary and widget code.

I'll open the research repo, record skill use, and load glossary plus TUI memory so naming stays aligned with existing terms.

The repo open is still running; I'll wait for it, then load glossary and TUI notes.

Research checkout is open. Next I’ll load glossary and TUI notes, then map how the prompt input widget, stacks, and property panel actually work.

The widget is `PromptInputBar`. I’ll map stacks and the property panel next, and check existing research-report conventions.

Docs call the inspector a Frontmatter Panel; I’ll trace that against “property panel” in code and how glossary terms are written.

I have the architecture and the name collisions. Next I’ll write the independent report with a ranked list and a glossary entry for the top pick.

The report is on disk. I’ll register it as a durable artifact and read the finalizer skill.

Artifact registration succeeded. I’ll confirm the label, then submit the finalizer.

**Canonize Prompt Bar.** Keep **prompt stack** for the panes, and call the header inspector the **Properties Panel**. Do not keep "prompt input widget", and do not invent a third name such as Composer.

The surface already has an informal name that guides, tests, and `PromptInputBar` agree on. Both words in the current heading fail: **widget** is Textual jargon, and **input** collides with typed `input:` fields, raw `<placeholder>` tags, `ace.prompt_inputs`, and the post-submit Prompt Inputs panel. The glossary body should teach that this "bar" holds a stack of panes plus an optional properties panel.

Full report: `research:202611/prompt_input_widget_naming__grk.md`  
Snapshot: `file:explicit:b47d5b0be4dc4c3039df456c` (source left in the research repo)

### Ranked names

1. **Prompt Bar** — recommended. Already the operator name; maps to `PromptInputBar`; sits next to Prompt Stash and Raw Prompt.
2. **Prompt Composer** — best semantic alternative (compose prompts + properties + panes). Would split widget / bar / composer, and collides with Cursor's model line plus PHP Composer.
3. **Composer** — one-word SASE voice, worse collisions (pager internals already use "composer").
4. **Prompt Dock** — accurate about bottom docking; macOS/Docker collision; not in current docs.
5. **Prompt Stage** — collides with auto-staged inputs.
6. **Prompt Pad** — undersells the stack, panel, and bound-macro targeting.
7. **Prompt Book** — theater metaphor; too private for agents.
8. **Launch Bar** — wrong scope (feedback, coder prompt, macro edit).
9. **Prompt Surface** — accurate and empty.
10. **Prompt Rack** — maybe a stack nickname; bad umbrella.
11. **Prompt Workbench / Studio / Forge** — product-y, too long.
12. **Prompt Input Widget** — reject. Keep only as a retired `aka`.

Child names inside the one term: **prompt stack** (keep), **Properties Panel** (alias Frontmatter Panel / property panel).

### Recommended glossary entry for #1

**Keyword:** `prompt-bar`

```markdown
# Prompt Bar

aka prompt bar, prompt input widget, prompt widget, prompt input

A prompt bar is the bottom-docked TUI surface where the operator writes,
stacks, and launches prompts. The class is `PromptInputBar`; the border title
is `Prompt`, or `Plan Feedback` / `Coder Prompt` in those modes. In prompt
mode the bar always holds a **prompt stack**: an ordered list of panes plus
shared YAML frontmatter, with at least one pane. Loading literal `---`
multi-agent text splits into panes labeled `agent 1`, `agent 2`, and so on;
`g-` / `Ctrl+G -` adds an empty bottom pane; `gj`/`gk` move focus and
`gJ`/`gK` reorder. Inactive panes stay compact, the active pane takes the
height, and whole-stack submit joins panes top-to-bottom. Auxiliary snippet
and mini-macro panes can sit in the same stack without launching as agents.
A `#name` macro swarm stays one pane until launch. Typed `---` never splits a
pane and never opens the properties panel.

The **Properties Panel** (implementation: `FrontmatterPanel`; also called the
frontmatter panel) sits above the stack and edits that shared frontmatter as
structured fields (`name`, `description`, `tags`, `input`, `macros`, `skill`,
`snippet`). `g=` / `Ctrl+G =` shows or focuses it; in the panel's rows mode
the same chord returns to the originating pane. `a` adds a property from the
core schema picker, `R` opens a live-validated raw-YAML escape hatch, and
local `macros:` helpers declared here are usable as `#_name` in every pane.
The panel auto-shows when leading frontmatter is lifted (multi-agent load,
editor-file return, targeted macro edit) and stays closed for a single
history item that has frontmatter but no segment separator.

The prompt bar is distinct from the [[glossary:prompt-stash]] (parked
drafts), the Prompts overlay (History / Stash / Trash), the
[[glossary:raw-prompt]] (what an agent receives at launch), and the
post-submit Prompt Inputs panel that fills raw `<placeholder>` tags and
required `input:` values. Feedback and coder-prompt bars reuse the same
widget without a stack or properties panel.
```
