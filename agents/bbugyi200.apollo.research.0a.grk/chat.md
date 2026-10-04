# Chat History - ace-run (research.0a.grk)

- **TIMESTAMP:** 2026-10-04 17:01:56 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.0a.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261004_164941.md`

## Prompt

%id(grk, clan=research.0a)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 4-researcher swarm.
The other researchers, `research.0a.cdx`, `research.0a.cld`, `research.0a.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__gem.md`. Your report will end in `__grk.md`.

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
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll research the existing macro input system independently and design an enum type that fits it. First I'll load the research/artifact skills and map how macros, completions, and LSP currently work.

I'll map the workspace, existing research files, and the current macro-input types so the design sits on real code rather than guesses.

Next I’ll read the macros memory, glossary, and source so the enum design matches how inputs, completion, and plugins actually work.

The input-type list is `word/line/text/path/int/bool/float`. I’ll trace how those types are declared, validated, completed, and exposed over LSP.

`InputType.ENUM` already exists for gates and loaders. I'll map what completion, LSP, and shared catalogs still lack versus that core type.

Enum already parses and validates. I’ll open sase-core and the editor path next, then trace completion, LSP, and named catalogs.

I'll open the research sidecar for the write, then draft the report from the enum, completion, and catalog evidence already collected.

A peer already used `architecture__gem`; I’ll write under a different stem and leave that file unread.

Artifact registration succeeded. I’ll pull the finalizer context and submit the research-sidecar commit.

**Keep `type: enum` and add named catalogs.** Do not invent a new input type. `enum` already parses, validates, and shows up in docs, gates, and the typed-input form. What is missing is completion, diagnostics, and shared vocabularies.

The report is at `sase/repos/research/202610/macro_enum_input_shared_catalogs__grk.md`, registered as `research:202610/macro_enum_input_shared_catalogs__grk.md` (`file:explicit:27ecb5f1c4fcdb4602d4d22a`).

Recommended design:

- Inline `choices:` stay a closed word-subtype of `word` (enforce no whitespace on values; labels are display-only).
- Reuse lives in `catalog:`, not in `type:` and not as a scalar `choices:` value. Ids are dotted names (`model`, `effort`, `github.pr_status`), resolved first-wins through project → user → plugin config → builtins.
- Reject `builtin@model_enum_values`. That sigil already names workers (`builtin@commit`) and collides with real values (`@large`).
- `catalog: model` is closed against the `%model` completion catalog. `%model` itself stays open-with-fallback.
- Ship in three slices: thread existing `choices` through TUI/LSP/mobile wire (they are dropped today), then named static catalogs, then live `model`.

The prompt bar and LSP currently treat enum like an untyped word: `MacroInputHint` has no `choices`, value completion always offers `true`/`false`, and LSP membership checks fall through to “valid.” Phase A alone makes enums work in the prompt widget and in nvim.
