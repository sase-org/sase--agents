# Chat History - ace-run (research.0a.cld)

- **TIMESTAMP:** 2026-10-04 17:05:10 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0a.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261004_164941.md`

## Prompt

%id(cld, clan=research.0a)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.0a.cdx`, `research.0a.grk`, `research.0a.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add support for a new `enum` macro input type in order to, for example,
add customizable completion for macro inputs in the prompt input widget and external
editors (via LSP support).

- Every input that has an enum type will need to specify the set of values that are
  allowed to be used for that enum. These values are just single-word strings, so enums
  are sort of like a sub-type of the existig `word` macro input type.
- We need to support re-using enum values so plugin providers and sase itself can share
  enum value sets. For example, this functionality will be required in order to allow
  users to specify that a macro they are defining has an input that only accepts a valid
  model string that is accepted by the `%model` directive. I'm imagining that we can use
  something like `builtin@model_enum_values` to specify that a macro input uses this type
  but you should think hard about the best way to do this.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'll start by exploring how macro inputs are currently defined and typed.

Notable: `InputType.ENUM` and `InputChoice` already exist. Let me see how far that existing support goes.

The enum type already partially exists (inline `choices`, added through notification-gate work). Let me read the loader, frontmatter, and properties code.

The macro LSP is a Rust binary (`sase-macro-lsp`) fed by catalogs passed through env vars, including a **model catalog**. Let me see how those catalogs are built.

Rust has a `macro_catalog` module. Let me read its types and parsing.

Rust has its own parallel macro catalog loader that already parses `choices`. Let me see whether the editor/LSP completion uses them.

A shared `<plugin>@<id>` grammar already exists (`src/sase/plugins/qualified_id.py`, "for every `use:` config consumer"). Now let me check the schema and workflow gaps for the existing enum type.

Status: surveying every loaded macro (home, project, plugins) through `sase macro list` to see which inputs would actually benefit from enums versus domain types.

I have what I need. Collecting exact line numbers for the citations before writing.

Writing the report now.

Let me verify one claim before registering: that the LSP's frontmatter parser rejects `type: string`.

Confirmed (`string` → `None` → diagnostic). Registering the report as an artifact.

Registration succeeded. Now the final declaration.

`uv.lock` changed in the main checkout. My `uv run` probably re-locked it, so let me inspect the diff before deciding.

The report is written to `sase/repos/research/202610/macro_enum_inputs_and_named_value_types__cld.md` and registered as artifact `explicit:0bc149771ece575c0104ab6f` with the label `research:202610/macro_enum_inputs_and_named_value_types__cld.md`.

**Main findings**

- **The `enum` input type already exists.** It shipped on 2026-08-07 as part of the notification-gate work: `type: enum` with inline `choices`, in both Python and Rust, documented in `docs/macros.md`. What's missing is the part you want: neither the prompt bar nor the LSP offers enum value completion. Both send `enum` to a generic type-hint path that suggests nothing.
- **The existing support has real bugs:**
  - **Python and Rust read YAML differently.** I reproduced this: `choices: [yes, no]` becomes `True`/`False` in Python, so `#x:yes` is rejected. The Rust LSP keeps `yes` and would suggest it.
  - **Longform workflow inputs drop `choices`**, so a longform `type: enum` can never load.
  - **Unknown types silently become `line` in Python.** So `type: model` and typos like `enmu` load without any error.
  - **The list of valid type names differs across five places** (two JSON schemas and three parsers). The schemas also have no `enum` or `choices` at all.
- **Usage across all 114 loaded macros:** inputs tied to live sets of values (models, beads, VCS prefixes, task types) outnumber fixed lists about 8 to 1. The biggest case is `#research_swarm`: it has nine model inputs typed as plain `word`. A typo like `claude_model=opsu` gets through, and `%model` then silently falls back to the default provider.

**Critique and the changes I propose (called out as R1–R7 in the report)**

- **A valid `%model` value isn't an enum.** `%model` accepts an open set of forms (`@alias@effort`, `provider/model`, nested OpenCode paths), and what's valid depends on the machine. Instead of `builtin@model_enum_values`, I recommend `type: model`, which works like the existing `type: agent`.
- **Builtin types should use bare names** (`model`, `effort`). Keep the `<plugin>@<id>` form, which already exists in `plugins/qualified_id.py`, for types declared by plugins.
- **Be strict with values a caller types and lenient with an author's defaults.** That way a default pointing at a provider that isn't installed doesn't break a macro on another machine.

**Recommended solution:** call the feature "named input types":

- Keep inline `type: enum` with `choices` for one-off lists.
- Add builtin types that match what each directive accepts: "if a directive accepts it, a macro input can be typed as it." Start with `model` and `effort`.
- Let users share fixed lists through a new `input_types:` section in `sase.yml`.
- Add a plugin hook modelled on task types later, once a second plugin needs one.
- Do the parsing, type lookup and validation in `sase-core` so the prompt bar, LSP and mobile all agree.

Suggested order: fix the bugs above first, then add enum completion everywhere, then `model`/`effort`, then config-declared lists, then plugin-declared lists.

My diagnostic `uv run` added a missing `mkdocs-redirects` entry to `uv.lock`. That change wasn't part of this task, so I put the file back the way it was. The only commit declared is the report in the research repo.
