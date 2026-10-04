- **AGENTS:**
  - [bbugyi200.apollo.research.0a.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.0a.final/README.md)

%clan(research.0a, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like
to add support for a new `enum` macro input type in order to, for example, add
customizable completion for macro inputs in the prompt input widget and external editors
(via LSP support).

- Every input that has an enum type will need to specify the set of values that are
  allowed to be used for that enum. These values are just single-word strings, so enums
  are sort of like a sub-type of the existig `word` macro input type.
- We need to support re-using enum values so plugin providers and sase itself can share
  enum value sets. For example, this functionality will be required in order to allow
  users to specify that a macro they are defining has an input that only accepts a valid
  model string that is accepted by the `%model` directive. I'm imagining that we can use
  something like `builtin@model_enum_values` to specify that a macro input uses this
  type but you should think hard about the best way to do this.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]])
%id:research.0a.final %m:@xlarge %wait:research.0a.cdx %wait:research.0a.cld
%wait:research.0a.grk %wait:research.0a.gem %q(1.5x, w=0.25) #gh:gh_sase-org__sase You
are the lead researcher: 4 independent researchers have reported on the request below,
and you will add your own research and merge every perspective into one consolidated
report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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
  something like `builtin@model_enum_values` to specify that a macro input uses this
  type but you should think hard about the best way to do this.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix in
   cdx, cld, grk, gem, belonging to this dispatch's `research.0a.cdx`,
   `research.0a.cld`, `research.0a.grk`, `research.0a.gem` dependencies, matching by
   `wait_name` and the canonical research label's existing `__<suffix>.md` suffix. Never
   reassign suffixes from list order. Open the research repo with `/sase_repo`, then
   read each report through its canonical research reference (or the `ref` field's
   `file:<id>` reference if the original has moved) using `sase artifact read`. Do not
   read predecessor chat transcripts. If the records above do not identify exactly one
   report per expected suffix, stop and report the missing or ambiguous input instead of
   guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest
   findings from every report above and your own research, resolve conflicts, cut
   duplication, and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker agent
   `research.0a.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.0a.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l
   "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails, report
   that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__gem.md
├── <name>__final.md
└── <name>_narration.md
```
