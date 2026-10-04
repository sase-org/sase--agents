# Chat History - ace-run (research.0a.image)

- **TIMESTAMP:** 2026-10-04 17:28:39 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** research.0a.image
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261004_164941.md`

## Prompt

%id(image, clan=research.0a) %m:gpt-6-astra
%wait:research.0a.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:c607abc33fb5151bce20d43b7756848f`

- **Node:** `agent-delta:20261004164946:6cdb2558bed0afac`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261004164946:6cdb2558bed0afac.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.0a, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to add support for a new `enum` macro input type in order to, for example,
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
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.0a.final %m:@xlarge
%wait:research.0a.cdx %wait:research.0a.cld %wait:research.0a.grk %wait:research.0a.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

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
  something like `builtin@model_enum_values` to specify that a macro input uses this type
  but you should think hard about the best way to do this.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.0a.cdx`, `research.0a.cld`, `research.0a.grk`, `research.0a.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
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
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.0a.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.0a.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

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

### Assistant

Reading the four reports (cdx and cld done); now grk and gem.

Read all four reports; now checking the main disagreements against the actual code.

Confirmed several existing enum defects (YAML coercion, invalid defaults accepted at load); now checking the Rust side and the `%model` resolver.

Verifying the plugin-sharing precedents next (qualified ids, task-type hooks, plugin config merging).

Checking the `plugins.required` rule and the macro corpus for real enum/model inputs.

Code claims verified. Reading the flags and macros reference memory so the rollout advice follows project rules.

Reports moved. Writing the consolidated report now.

Citations check out. Registering the consolidated report.

Registration succeeded. Submitting the final declaration.

The consolidated report is written and registered as `research:202610/macro_enum_inputs_named_types/macro_enum_inputs_named_types__final.md` (ref `file:explicit:c5093cfb111bffb51315b00d`). The four reports moved into the same folder under their original suffixes, and the research repo is declared for commit. I did not create `<name>.md` or `<name>_narration.md`, which the layout lists; the linker step publishes `<name>.md`, and nothing in the steps asked for the narration file.

**Findings**

- **`enum` already exists but is unfinished.** It shipped in August 2026, but nothing completes enum values in the prompt bar or the LSP. Every hint wire drops `choices`, and the editor's argument check accepts any enum value.
- **The current enum has real bugs.** I reproduced them:
  - `choices: [yes, no]` loads as `True/False`, so `#x:yes` is rejected.
  - An invalid default such as `turbo` loads and is used anyway.
  - Empty, whitespace and `null` values are accepted.
  - Long-form workflow inputs drop `choices`.
  - Unknown types like `type: enmu` silently become `line`.
  - The JSON schemas don't list `enum` at all.
- **The model example is not an enum.** `%model` accepts an open grammar and silently falls back to the default provider for unknown names. Today, `claude_model=opsu` in `#research_swarm` launches on the wrong provider without complaint.
- **The rule a model input should enforce already exists.** `sase doctor -C config.model_macros` has a check (`_model_token_routes`) for "routes without silent fallback". None of the four reports noticed it.

**Where I sided against the majority:** three researchers put the shared reference in a field on the enum (`choices: {use: …}`, `catalog:`, `enum:`). One proposed named types, and I went with that:
- `type: agent` already works this way.
- The short input syntax (`name: <type>`) then works without the long form.
- It doesn't claim models are a closed list.
- It matches your own phrasing, "uses this type".

**Recommended solution**

```yaml
mode:    {type: enum, choices: [fast, thorough]}   # inline enum (exists today)
model:   {type: model, default: "@large"}           # accepts what %model routes without fallback
effort:  effort                                     # closed list matching %effort
edition: sase-research-artifacts@audio_edition      # enum shared by a plugin
```

- **Built-in types use bare names** (`model`, `effort`). I'd reserve every directive value-role name now so future built-ins can't collide with anything. `builtin@model` would be accepted as an alias, and `builtin@model_enum_values` becomes just `model`.
- **Plugins share enums** in an `input_types.yml` file next to their `macros/` folder. Rust reads it directly, so the TUI and the LSP always see the same types.
- **Validation, resolution and completion live in sase-core.** Python only discovers plugins and builds the model data.
- **Order:**
  1. Fix the existing enum bugs.
  2. Complete and check enum values in both the TUI and the LSP.
  3. Add the `model` and `effort` types.
  4. Add plugin-shared enums, with `audio_edition` as the first user.
- **Leave out for now:** enums defined in your own config, suggestion-only inputs, and plugin callbacks. Nothing uses them yet.

**Requirement changes** (listed explicitly in §6 of the report):
- Treat this as finishing the existing enum rather than adding a new type.
- A model input is its own type, not an enum.
- Enum values are enforced as single words in macros and workflows, but not in gate inputs.
- Each choice can carry a `description`.
- A bad default is an error for closed enums but only a warning for `model`.

The `macros.md` memory note is stale: its input-type list omits `enum`, `agent` and `code`. The report mentions it, but I didn't file a task for it.

---

%macros_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<stem>_infographic.png` in the same directory, where
`<stem>` is the source file's stem with any trailing `__final` removed (so
`topic__final.md` becomes `topic_infographic.png`; other stems are unchanged).
Create it without overwrite. If it already exists, stop and report the collision.


## Response

I’ll read the registered report and use the imagegen skill to create the infographic beside it, after checking for a filename collision.


I’m using the SASE repository and audited artifact workflows to access the source report and save the image in its research directory.


The destination is available. The infographic will highlight the report’s central recommendation: finish the existing enum support, add named types for domains such as `model`, and share validation and completion through Rust.


The infographic is generated, and I’ve checked its text and diagrams against the report. I’ll save it without overwriting any existing file and use the sase_artifact skill to register a durable copy.


The PNG is saved beside the report and registered as an artifact. I’m using the sase_final skill to declare the completed repository change.


Created [macro_enum_inputs_named_types_infographic.png](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/macro_enum_inputs_named_types/macro_enum_inputs_named_types_infographic.png) beside the report without overwriting.

Generated with built-in imagegen ([prompt](/tmp/sase-enum-infographic-3614112-prompt.txt)). Registered as [file:explicit:bf2cf10631a4122895eb6f2e](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261004164947/macro_enum_inputs_named_types_infographic-1a56845386a7.png).
