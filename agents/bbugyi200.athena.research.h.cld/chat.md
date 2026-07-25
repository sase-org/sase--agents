# Chat History - ace-run

- **TIMESTAMP:** 2026-07-17 13:22:15 EDT
- **MODEL:** claude/opus
- **AGENT:** research.h.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260717_131238.md`

## Prompt

%name:research.@.cld %m:@research_b %g:research %family(research.@.final, role=researcher) #gh:gh_sase-org__sase I would like to add support to the fork xprompt workflow for accepting multiple sase agent names as arguments. In this case we would construct an ideal chat message to indicate to the next agent that it is forking off of two or more other agent chats. Can you do some research to help me understand what this ideal pre-constructed prompt looks like? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research the fork xprompt workflow to understand how it currently constructs prompts for forking off a single agent chat, then determine what the ideal prompt looks like for multiple agents. Let me start by exploring the codebase.

Found the key files. Let me read the fork xprompt definitions and related machinery.

Let me read the chat history loader and understand the xprompt input/arg system. I'll delegate broader exploration in parallel.

I'll investigate the xprompt workflow system. Let me start by exploring the relevant files in parallel.

Let me examine the schema and find the core workflow parsing modules.

I'll investigate the SASE chat-resume system. Let me start by reading the key files in parallel.

While the research agents work, let me examine the multi-agent prompt module and check for prior related research.

Let me look at the core models and parsing code.

Now let me investigate the `xprompts_enabled` directive parsing and search for any multi-source/merge fork concepts.

Now let me look at the InputArg model, the loader_parsing module, and the invocation argument parsing.

Let me read the disabled-regions parser, the directives module, and fork_by_chat.yml.

The research directory is the `sase--research` sidecar repo. Per the project rules, I must open it via the `/sase_repo` skill to get the canonical path before writing. Let me do that while I continue gathering context.

Now let me find the invocation argument parsing (the `#fork(name=foo)` / `#fork foo` syntax) and the agent-type resolution/completion.

Let me look at the processor's disabled-region handling, the directives stripper, and search for any hint of multi/multiple fork args.

Let me read the invocation argument parsing files.

Now let me look at how parsed args are bound to InputArgs and the agent-type resolution/completion.

The canonical path matches. Now let me understand how the injected history combines with the user's actual new query, and look at prior related research.

Let me read the Jinja templating/binding code, prompt_inputs, and the directive completion for agent type.

Let me read the fork resolution script and check the processor's disabled-region-start handling.

Let me look at the agent-type completion and the templating in workflow steps (python/prompt_part rendering).

Let me read the resume-name resolver to confirm current single-target behavior.

Now let me look at how python steps are rendered (templating) and how step outputs are referenced, plus the agent-arg completion wiring.

I have a complete picture. Let me confirm one metadata detail.

Let me check for any variadic/list support and how workflow inputs are bound into the execution context.

Let me read the render context building in workflow_runner and the render_template utility.

Let me find where full-workflow inputs (positional + named) get bound into the initial execution context.

Let me verify a key detail: whether saved chat transcripts retain the raw `#fork:` reference (re-expanded at read time) or inline the rendered history. This determines how a multi-agent fork ref must be handled.

Let me look at existing tests for fork and the xprompt arg-parsing to nail down multi-arg invocation syntax.

Research complete. Here is the structured summary.

# SASE Chat-Resume System — Research Findings

## 1. `load_chat_for_resume` and the "history" text format

**File:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/history/chat.py`, lines 502-565.

The function loads a chat `.md` file, parses it into `(prompt, response)` turns, recursively inlines any nested fork/resume references, sanitizes prompts, and emits flat `**User:**` / `**Assistant:**` blocks.

Core output-formatting loop (lines 560-565):
```python
parts = []
for prompt, response in expanded_turns:
    clean_prompt = _sanitize_resume_prompt(prompt)
    parts.append(f"**User:**\n\n{clean_prompt}\n\n**Assistant:**\n\n{response}")

return "\n\n---\n\n".join(parts)
```

**Precise output format:**
- One block per turn, blocks separated by `\n\n---\n\n`.
- Each block is literally: `**User:**\n\n<sanitized prompt>\n\n**Assistant:**\n\n<response>`.
- **No header, no agent name, no timestamps, no model info.** The output is purely the interleaved conversation. There is nothing identifying *which* agent produced it. (The identifying banner/metadata exists only inside the source `.md` file — see section 2 — and is discarded by `_parse_chat_turns`.)
- If parsing yields no turns, it falls back to returning the raw file `content` (line 537-538).

**Helpers it calls (all in the same file):**
- `_load_chat_history(file_ref, increment_headings=False)` (lines 568-598): resolves basename-or-path, reads the file. `load_chat_for_resume` deliberately loads **without** heading increment (docstring line 508-510) to prevent heading inflation across repeated resumes.
- `resolve_chat_file_path` / `get_chat_file_path` (lines 260-269, 249-257): shard-aware path resolution.
- `_parse_chat_turns(content)` (lines 429-480): finds `#{1,6} Prompt` / `Response` heading pairs at matching levels, extracts bodies, and **sorts by heading depth (deepest = oldest)** to reconstruct chronological order. Returns `list[(prompt, response)]`.
- `_find_resume_refs(prompt)` (lines 102-117) + `_RESUME_REF_RE` (lines 27-34): finds `#fork` / `#fork_by_chat` / legacy `#resume` / `#resume_by_chat` refs. **Important for your extension: the regex captures exactly ONE argument per reference** (colon or paren syntax, single value — no comma-list support).
- `_resolve_resume_to_chat_path(xprompt_name, argument)` (lines 120-154): for `*_by_chat`, treats arg as a path; for `fork`/`resume`, resolves the agent name → reads its `done.json` → `response_path`.
- Recursion (lines 540-558): for each turn's prompt refs, if the resolved path is unvisited it calls `load_chat_for_resume(resolved_path, _visited)` recursively, re-parses the returned flat text via `_parse_flat_turns`, and **extends** the turn list. `_visited` (set of absolute paths) provides cycle detection. The fork/resume ref token is then stripped from the prompt (line 555). This is the one place today where *multiple* histories get concatenated — but only transitively (a parent's own resume ref), never two co-equal parents at the top level.
- `_sanitize_resume_prompt(prompt)` (lines 42-99): strips sase control syntax from user prompts so the transcript reads as clean natural language — removes `%name` directives + `%xprompts_enabled` markers, `#`/`#!` xprompt refs, unrendered Jinja markers, and tidies whitespace (fenced code blocks are protected throughout). **Assistant responses are intentionally left untouched.**

## 2. Storage, identification, and telling two agents' transcripts apart

**Filename encoding** (`generate_chat_filename`, lines 211-246): basename = `-`.join of `[branch_or_workspace, workflow, optional agent, timestamp]`, e.g. `myfeature-run-buildbot-251128104155`. Stored sharded under `~/.sase/chats/YYYYMM/<basename>.md` (`save_chat_history`, lines 357-360; sharding via `sharded_path`).

**In-file metadata banner** (`save_chat_history`, lines 364-395, and `_format_transcript_metadata_blocks`, lines 294-314). Every transcript begins:
```
# Chat History - <workflow> (<agent>)

- **TIMESTAMP:** <display_timestamp>
- **MODEL:** <provider/model>
- **AGENT:** <sase agent name>
- **PROMPT:** `<multi-agent prompt path>`
```
(`MULTI_AGENT_PROMPT_METADATA_LABEL = "PROMPT"`, from `src/sase/history/multi_agent_prompt.py:8`.) Then `## Previous Conversation` (if resuming), `## Prompt`, `## Response`.

**chat_path vs response_path concept** — two distinct JSON pointers per agent, both consumed when resolving a fork target:
- `agent_meta.json["chat_path"]` — the live/most-recent transcript path for any agent (running or done).
- `done.json["response_path"]` — the final transcript path for a **completed** agent.

Resolution order (both `_resolve_resume_to_chat_path` in chat.py lines 136-152 and `resolve_chat_ref` in chat_catalog.py lines 262-282, and `agent_chat_from_name._resolve_agent_chat_path` lines 22-43): **completed agent's `done.json["response_path"]` first, then any agent's `agent_meta.json["chat_path"]`.**

**Cataloging** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/history/chat_catalog.py`:
- `ChatTranscriptInfo` dataclass (lines 50-64): `path`, `absolute_path`, `basename`, `mtime`, `size_bytes`, `workflow`, `agent`, `timestamp`, `prompt_snippet`, `response_snippet`.
- `_parse_header` (lines 89-95) + `_HEADER_RE` (lines 35-38) parse `workflow` and `agent` back out of the `# Chat History - <workflow> (<agent>)` banner.

**Telling two agents apart:** Yes — agent identity is available, but only from the *source file / catalog*, not from `load_chat_for_resume`'s output. The `agent` name lives (a) in the filename, (b) in the H1 banner, and (c) in the `**AGENT:**` metadata row. Since `load_chat_for_resume` discards all of that and returns unlabeled `**User:**/**Assistant:**` blocks, a multi-parent "merge" would need to inject per-source attribution itself (e.g. read each source's `ChatTranscriptInfo.agent` / banner and prepend a labeled sub-heading before each source's turns).

## 3. Existing multi-source / merge / multi-parent fork — DOES NOT EXIST

There is **no existing notion of forking off two-or-more prior agents simultaneously.** Every mechanism is strictly single-parent:

- `src/sase/xprompts/fork.yml` and `fork_by_chat.yml`: each takes exactly one input (`name` / `path`), calls `load_chat_for_resume` once on one file, and wraps the single result. No list handling.
- `src/sase/agent/multi_prompt_reference_resume.py`: the name "multi_prompt" refers to launching **multiple agents sequentially from one command** (see `src/sase/agent/multi_prompt.py:4` — "segment separators for launching multiple agents sequentially"), **not** one agent with multiple parents. `_RESUME_REF_RE` (lines 6-13) captures a single `colon` or single paren arg. `has_bare_resume_reference` / `rewrite_bare_resume_references` rewrite a bare `#fork` to `#fork:<one agent_name>`.
- `src/sase/agent/multi_prompt_reference_allocator.py`: `first_resume_agent_name(prompt)` (used at line 84) returns **the FIRST** resume target only; `planned_name_for_prompt` handles exactly one `resume_target`. Its "template group" machinery allocates related *names* for a batch launch — unrelated to multi-parent context.
- `src/sase/agent/names/_resume.py`: `first_resume_agent_name` (lines 66-77) and `first_fork_agent_name` (lines 80-94) both **return after the first match**. Fork-derived naming is single-parent: `resume_agent_name_template(base) = f"{base}.f@"` (lines 148-150) — a child name is derived from exactly one base parent.
- The only transitive multi-history behavior is the recursion in `load_chat_for_resume` (section 1), which follows a *chain* of single parents, not a top-level *set* of co-parents.
- No `merge.yml` xprompt exists (full listing of `src/sase/xprompts/` shows only `fork.yml` and `fork_by_chat.yml` as fork/resume-related). Grep for merge/multi-parent/co-parent across `history/`, `agent/`, `xprompts/` returned only unrelated hits (git merge, `pending_family_parents` for agent-family attach, etc.).

**Implication for your extension:** A multi-parent fork is genuinely new. The cleanest insertion points are: (a) a new `merge.yml`-style xprompt (or extending `fork.yml` input to accept a list) that calls `load_chat_for_resume` once per source and concatenates; and (b) the single-arg `_RESUME_REF_RE` regexes in `chat.py` (lines 27-34), `multi_prompt_reference_resume.py` (lines 6-13), and `names/_resume.py` (lines 19-35) plus the single-target `first_resume_agent_name` return would all need to become list-aware for name-allocation / implicit-`%wait` to track multiple parents. Note also that the current output format carries no per-source attribution, so a merge should add source headers itself.

## 4. `%xprompts_enabled:false` / `%xprompts_enabled:true` directive markers

These mark a **"disabled region"** — a span of prompt text that must be shielded from xprompt/directive expansion (so a resumed transcript containing literal `#foo`, `%bar`, `{{ }}` doesn't get re-interpreted as live control syntax).

**Primary parser:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/_disabled_regions.py`.
- `_DISABLED_REGION_RE` (lines 11-14) matches from a line-leading `%xprompts_enabled:false` up to the next `%xprompts_enabled:true`.
- `protect_disabled_regions(text, regions)` (lines 19-39): replaces each region (markers included) with a null-byte placeholder `\x00XPD_<idx>\x00`, so expansion passes skip it.
- `unprotect_disabled_regions` (lines 52-68): restores placeholders **keeping the markers** so later stages can still see them.
- `strip_disabled_region_markers` (lines 71-88): final cleanup that deletes the `%xprompts_enabled:false/true` marker lines themselves.
- `strip_disabled_regions` (lines 47-49) / `disabled_region_ranges` (lines 42-44): remove or locate whole regions.

**Where it's wired in / other parse sites:**
- `src/sase/xprompt/processor.py:373-375` protects disabled regions before the expansion loop; lines 43-44 + 517-527 (`_DISABLED_REGION_START_RE`) ensure a marker that lands mid-line after expansion is moved to its own line so the protect/strip regexes can match it.
- `src/sase/xprompt/directives.py:66-99` (`extract_prompt_directives`, `strip_disabled_markers=True` by default) strips the markers when extracting `%name` directives; can be deferred (`strip_disabled_markers=False`) for multi-phase pipelines.
- `src/sase/xprompt/workflow_executor_steps_embedded_types.py:15-18` — its own `_DISABLED_REGION_START_RE` for embedded workflow steps.
- `src/sase/xprompt/xprompt_inspect.py:65` documents that these regions (like fenced/inline code) are excluded from inspection.
- Consumers that protect regions before their own lexical scans: `multi_prompt_reference_resume.py`, `multi_prompt_reference_allocator.py`, `names/_resume.py:12`.
- The sanitizer `_sanitize_resume_prompt` in chat.py (line 79) also calls `strip_disabled_region_markers` so stored transcripts render cleanly.

**Net effect in the fork wrapper:** the `%xprompts_enabled:false` … `%xprompts_enabled:true` envelope around `# Previous Conversation` guarantees the injected historical text is treated as inert content, while `# New Query` (after the `:true` marker) is processed normally. For a multi-parent merge you can reuse this exact envelope — one region wrapping all merged sources, or one region per source with attribution headers between them.

This is squarely xprompt territory. Per project rules I should review the xprompts long-term memory. Let me do that while the subagents finish.

The chat-resume research is thorough. Let me run the memory read command and check on the first research agent.

Very helpful. The grammar already supports `#fork:a,b` and `#fork(a, b)`. Let me verify one central detail for the recommendation: whether saved transcripts keep the raw `#fork:` ref (re-expanded at read time) or store expanded history inline — this determines whether `_RESUME_REF_RE` needs to become multi-arg-aware.

I now have a complete picture of the xprompt input system. Here is my structured report.

---

# XPrompt Workflow Input System — Research Findings

## Summary answer to the core question
There is **no variadic / list / repeated-value support for a single input today**. Each declared input binds to exactly one scalar string value (by name or by one positional slot). To make `fork.yml` accept two-or-more agents you would either declare multiple distinct inputs (`name1`, `name2`, …) or accept one `text`/`line` input and split it inside a step — the framework has no `nargs`/`list: true`/splat mechanism.

---

## 1. Where `input:` blocks are parsed & validated, and the supported types

**Type enum** — `src/sase/xprompt/models.py:22-33`:
```python
class InputType(Enum):
    WORD = "word"    # Single word, no whitespace
    LINE = "line"    # Single line, no newlines
    TEXT = "text"    # Multi-line text (any content)
    PATH = "path"    # Single-line file path
    AGENT = "agent"  # Agent name, same value rules as word
    INT = "int"
    BOOL = "bool"
    FLOAT = "float"
```

**String→enum mapping** — `src/sase/xprompt/loader_parsing.py:75-96` (`parse_input_type`). Accepted spellings: `word`, `line`, `text`, `path`, `agent`, `int`/`integer`, `bool`/`boolean`, `float`. Anything unknown silently defaults to `InputType.LINE`.

**The `InputArg` dataclass** (fields `name`, `type`, `default`, `is_step_input`, `output_schema`, `description`) — `src/sase/xprompt/models.py:66-148`. Its `validate_and_convert(value: str)` (lines 88-148) is the per-value validator: it takes a single `str` and returns a single scalar. There is no code path that accepts or returns a list.

**Parsing entry points** (two near-duplicate parsers):
- Workflow-level: `src/sase/xprompt/workflow_loader_parse.py:21-65` (`parse_workflow_inputs`) — longform list `[{name, type, default, description}]` or shortform dict.
- Front-matter / xprompt-level: `src/sase/xprompt/loader_parsing.py:262-305` (`parse_inputs_from_front_matter`) plus shortform helpers `parse_shortform_inputs` (134-157) and `_parse_shortform_input_metadata` (119-131).

**JSON schema** (editor validation / LSP) — `src/sase/xprompts/workflow.schema.json:9-72`. The `type` enum there is `["word","line","text","path","agent","int","integer","float","bool","boolean","string"]`. Note `string` appears in the schema enum but is **not** in `parse_input_type`'s map, so a `type: string` would fall through to `LINE` at runtime.

`fork.yml`'s input uses the object-shorthand form (`name: {type: agent, default: null, description: ...}`), parsed by the shortform path.

---

## 2. Variadic / multiple / list support — does not exist

Confirmed by:
- `InputType` has no list/array member (`models.py:22-33`).
- `validate_and_convert` is strictly `str -> scalar` (`models.py:88-148`).
- No `nargs`, `list:`, `variadic`, `splat`, `is_list`, or `repeated` tokens anywhere in `src/sase/xprompt/` or `agent/prompt_inputs.py` (grep returned only unrelated hits like "multiple references" and directive-level multiplicity).

**Positional binding is strictly one-value-per-input** — `src/sase/xprompt/workflow_runner.py:503-508`:
```python
# Map positional args to input names
for i, value in enumerate(positional_args):
    if i < len(workflow.inputs):
        input_arg = workflow.inputs[i]
        if input_arg.name not in args:
            args[input_arg.name] = value
```
Extra positionals beyond `len(workflow.inputs)` are simply dropped from the named `args` dict (they never map to any input). The same one-to-one logic is repeated in the simple-xprompt path at `workflow_runner.py:437-441` and in the xprompt-expansion path at `_jinja.py:120-139`.

The only "collect into a list" behavior in the codebase is for **prompt directives** (e.g. `%model`, `%wait`), not xprompt inputs — see `src/sase/xprompt/_directive_types.py:36` ("Directives that allow multiple occurrences (values are collected into a list)"). That machinery is separate from the `input:` system.

**Implication for extending `fork.yml`:** the supported approach is multiple scalar inputs, e.g.
```yaml
input:
  name: {type: agent, default: null}
  name2: {type: agent, default: null}
```
invoked as `#fork(name=a, name2=b)` or positionally `#fork(a, b)`. A single input cannot absorb both. Alternatively, one `type: text`/`line` input and split on whitespace/comma inside the `python:` step.

---

## 3. Invocation argument syntax & where it is parsed

**Lexer (regex) for `#name...` references** — `src/sase/xprompt/_parsing_references.py:15-44`. The reference pattern is assembled from fragments; the argument fragment is lines 29-33:
```python
XPROMPT_REFERENCE_ARGUMENT_FRAGMENT = (
    r"(?:(?P<open_paren>\()|:"
    r"(?P<colon_arg>`[^`]*`|\$\([^)]*\)|\{\{[^}]*\}\}|\{[^}]*\}|[a-zA-Z0-9_.~,+/-]*[a-zA-Z0-9_~+/-])"
    r"|(?P<plus>\+))?"
)
```
`XPromptReference.parse_arguments()` (lines 88-98) dispatches to the workflow arg parser.

**Argument grammar / value parser** — `src/sase/xprompt/_parsing_args.py`:
- `parse_workflow_reference` (261-333) recognizes the supported syntaxes: `name(arg1, key=value)` (paren, 289-313), `name:value` / `name: text` / `name:: text` (colon, 315-330), `name+` → `["true"]` (plus, 279-286), and plain `name`.
- `parse_args` (336-419) tokenizes the inside-paren string by commas — respecting quotes `"..."`/`'...'` and text blocks `[[...]]` — then classifies each token via `_parse_named_arg` (190-230): a token is **named** if it contains a top-level `=` (→ `name=value`), otherwise **positional**.

So both `#fork(name=foo)` (named) and `#fork(foo)` / `#fork:foo` (positional) are valid; the positional one binds to the first declared input (`name`) via the position loop in section 2. Multiple comma-separated positionals are already parseable syntactically (`#fork(a, b)` yields `positional=["a","b"]`) — they just have nowhere to bind unless a second input exists.

Reference-to-workflow resolution and the final positional→name mapping happen in `src/sase/xprompt/workflow_runner.py` (`_parse_standalone_ref` ~73-77; `execute_workflow` binding at 500-513).

---

## 4. How `type: agent` is resolved / validated + TUI completion

**Runtime validation** — `type: agent` is validated **identically to `word`**: `models.py:100-105` groups `{InputType.WORD, InputType.AGENT}` together and only rejects values containing whitespace; it does **not** verify the agent exists. The value is passed through as a raw string.

**Actual agent resolution is deferred to the step body.** In `fork.yml` the hidden `resolve` step calls `sase.scripts.agent_chat_from_name.main([name])`, which performs the real name→chat lookup at execution time. So `type: agent` = "word-shaped token, completed against live agents in the TUI, resolved later by the script."

**TUI completion wiring for the agent type:**
- Completion-kind selection — `src/sase/ace/tui/widgets/_xprompt_arg_assist_detection.py:216-230` (`_completion_kind_for_input`): `type == "agent"` → `"xprompt_arg_agent"`.
- Candidate builder — `src/sase/ace/tui/widgets/_file_completion_xprompt_args.py:42-47` routes `xprompt_arg_agent` to `build_agent_arg_completion_candidates` in `directive_completion.py:304-336`, which calls `filter_agent_completion_candidates(agent_candidates, partial)` (from `sase.ace.tui.agent_completion`) to list currently-visible agent names.

**Important nuance for a 2-input `fork`:** the paren-completion logic only auto-offers agent-name completion when the xprompt has **exactly one** input — `_xprompt_arg_assist_detection.py:279-291`:
```python
if len(entry.inputs) == 1:
    single_input = entry.inputs[0]
    completion_kind = _completion_kind_for_input(single_input)
    if completion_kind == "xprompt_arg_agent":
        return XPromptArgCompletionContext(..., completion_kind=completion_kind, ...)
```
With two inputs, bare `#fork(` paren completion instead offers **named-arg names** (`xprompt_arg_name`, lines 292-299); agent-name completion only kicks in after you type `name=` (the `name_part=value_part` branch at 301-318 re-derives the per-input kind). By contrast, **colon** syntax `#fork:a,b` completes each comma-separated position against its input's type (`_colon_completion_context`, 233-257 + `_colon_active_input_index`, 332-341), so a second agent-typed positional *would* get agent completion there. This is worth accounting for if you extend to two agents and care about TUI assist.

The compact hint label rendering (`name?: agent`, required styling) is in `src/sase/ace/tui/widgets/_xprompt_arg_assist_inputs.py:38-92`.

---

## 5. Templating in `python:` / `prompt_part:` steps

**Jinja environment + `tojson` filter** — `src/sase/xprompt/workflow_executor_utils.py`. `create_jinja_env` defines the custom `tojson` filter (booleans → `True`/`False`, else `json.dumps`) at ~lines 30-44, and `render_template(template, context)` (47-66) renders any step string against the accumulated context, merging `get_global_template_vars()` (provides `root`) first:
```python
env = create_jinja_env()
merged = {**get_global_template_vars(), **context}
jinja_template = env.from_string(protected_template)
rendered = jinja_template.render(merged)
```

**Where each step kind is rendered:**
- `python:` steps — `src/sase/xprompt/workflow_executor_steps_script.py:250`: `rendered_code = render_template(step.python, self.context)`, then executed via `subprocess … [sys.executable, "-c", rendered_code]`. This is why `fork.yml` writes `name = {{ name | tojson }}` — the filter emits a valid Python literal (`"foo"` or `null`→`None`... note: `tojson(None)` yields `null`, which is why the YAML relies on the value being a JSON literal assigned to a Python variable; a `None` default renders as `null` which is *not* valid Python — in practice `default: null` flows through as the Python `None` only because `_tojson` returns `json.dumps(None)` = `"null"`; the guard `name if name else []` at fork.yml:15 handles the falsy case).
- `bash:` steps — same helper at `workflow_executor_steps_script.py:94`.
- `prompt_part:` / `agent:` / `prompt:` steps — rendered on the prompt-expansion side; simple xprompts render their `prompt_part` content via the same `render_template` in `workflow_runner.py:447-448`, and embedded expansion lives in `src/sase/xprompt/workflow_executor_steps_embedded_expand.py`. The xprompt-reference expansion path uses `substitute_placeholders` / `_render_jinja2_template` in `src/sase/xprompt/_jinja.py:169-211` (Jinja context there also exposes positional args as `_1`, `_2`, `_args`).

**How step outputs like `resolve.path` are referenced:** each step's parsed output is stored in the executor context under the step's name — `workflow_executor_steps_script.py:399-401`:
```python
step_state.output = output
self.context[step.name] = output          # e.g. context["resolve"] = {"path": ...}
self.state.context = dict(self.context)
```
The output shape comes from the step's `output:` declaration (`resolve` has `output: { path: text }`, parsed by `parse_output_from_front_matter`). So `{{ resolve.path | tojson }}` is plain Jinja attribute/key access into that dict. Output parsing formats (JSON / `key=value` / plain `_output`) are handled by `parse_bash_output` (`workflow_executor_utils.py:69-116`), and value coercion by `coerce_output_types`.

**Static reference validation** (compile time) — `src/sase/xprompt/workflow_loader_parse.py:324-483` (`validate_workflow_variables` / `_validate_condition_refs`) uses the regex `\{\{\s*([a-zA-Z_]\w*(?:\.[a-zA-Z_]\w*)?)\s*` to check that any `step.field` reference names a real, already-executed step, and tracks input usage. Note this regex only captures a **single** `.segment`, so deep references like `{{ a.b.c }}` are only partially validated.

---

## Key file reference list (all absolute)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompts/fork.yml` — the target xprompt.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/models.py` — `InputType`, `InputArg.validate_and_convert`, `XPrompt`.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/loader_parsing.py` — `parse_input_type`, shortform/longform input parsing.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_loader_parse.py` — `parse_workflow_inputs`, `parse_workflow_step`, static var validation.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_models.py` — `Workflow`, `WorkflowStep` dataclasses.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompts/workflow.schema.json` — JSON schema (type enum, step rules).
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/_parsing_args.py` — invocation arg tokenizer/`parse_args`/`parse_workflow_reference`.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/_parsing_references.py` — `#name(...)` reference regex/lexer.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py` — positional→input binding, `execute_workflow`.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/_jinja.py` — `validate_and_convert_args`, xprompt Jinja rendering.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_executor_utils.py` — `render_template`, `tojson`, `parse_bash_output`.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_executor_steps_script.py` — python/bash step rendering + output→context storage.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/agent/prompt_inputs.py` — launch-time frontmatter input collection/coercion.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/widgets/_xprompt_arg_assist_detection.py` — cursor detection, per-position completion kind, the single-input agent-completion special case.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/widgets/directive_completion.py` — `build_agent_arg_completion_candidates`.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/widgets/_file_completion_xprompt_args.py` — routes `xprompt_arg_agent` to agent candidates.
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/widgets/_xprompt_arg_assist_inputs.py` — input hint labels.

No files were modified (read-only).

I now have a complete picture from both research agents plus my own reading. Let me verify the two exact touchpoints I'll cite in the recommendation — the single-arg colon regex in `chat.py` and the naming template — then write the research doc.

All confirmed. I have everything needed. Now let me write the research document.

I've researched the fork xprompt system end-to-end (workflow definition, chat-resume machinery, invocation grammar, and re-fork recursion) and written the analysis to:

`sase/repos/research/202607/multi_agent_fork_prompt_design.md`

Here's the essence.

## How single-agent fork works today

`#fork:builder` runs three hidden steps in `fork.yml`: **resolve** name→chat path, **load** via `load_chat_for_resume` (flat `**User:**`/`**Assistant:**` turns), **inject** wrapped as:

```
%xprompts_enabled:false
# Previous Conversation

<flat turns>

---

%xprompts_enabled:true
# New Query
```

The critical gap for multi-agent: **`load_chat_for_resume` output has zero attribution** — no agent name, no timestamp. Concatenating two transcripts naively would read as one indistinguishable blur.

## The ideal pre-constructed prompt (N≥2)

Add three things — provenance, boundaries, framing — and reuse everything else:

```
%xprompts_enabled:false
# Previous Conversations

You are forking from 2 prior agent conversations. Each `## Conversation` section
below is a complete, independent transcript produced by a different agent working
separately. Treat them as parallel context you are merging: draw on all of them to
answer the new query, and when they disagree, reconcile the difference explicitly
rather than silently picking one.

## Conversation 1 of 2 — agent `auth-refactor`

**User:** … **Assistant:** …

## Conversation 2 of 2 — agent `db-migration`

**User:** … **Assistant:** …

---

%xprompts_enabled:true
# New Query
```

The preamble names the situation and gives a conflict-resolution rule; each `## Conversation K of N — agent \`name\`` header supplies provenance and boundaries; order follows the order the user listed them (intentional, not recency). **N=1 stays byte-identical** to today, so it's purely additive.

## Recommended solution

Extend `#fork` in place (not a separate `#merge`), keep a single `type: agent` input, make **`#fork:a,b` the canonical multi form**. This works with *no schema change* because the colon grammar already delivers `"a,b"` as one value and agent-typed validation rejects only whitespace, not commas. Four localized edits:

1. `agent_chat_from_name.py` — resolve each comma-separated name → ordered `{name, path}` list
2. `fork.yml` `load_history` — loop sources, build the labeled block (N=1 = legacy format)
3. **`chat.py` `_RESUME_REF_RE`** — its colon capture stops at the first comma, so re-forking a merged agent would silently drop parents; must become comma-aware and resolve to a *list* of paths (the least obvious but correctness-critical change)
4. `names/_resume.py` — mirror the comma-aware regex for name allocation / implicit waits

Notable constraint: paren form `#fork(a, b)` tokenizes on commas and only binds the first with a single input, so v1 should document colon as the multi form. Open questions (paren-multi, live-parent waits, dedup of shared ancestors, per-conversation timestamps) are listed at the end of the doc.

Since this only created a markdown file in the research sidecar repo (no source changes in the sase workspace), `just check` isn't applicable.

I made these changes this session (the research markdown file), so I'll commit it. Let me first navigate to the research repo and check its status.

The untracked research file is present. Let me commit it via the commit skill.

I'll follow the skill steps. First, record the skill usage.

The file is a research doc. Now I'll write the commit message file.

The commit succeeded. Let me verify the repo is clean and pushed.

Committed and pushed — the research repo is clean and in sync with `origin/main`.

## Summary

I researched how the `#fork` xprompt workflow injects a single prior agent's conversation into the next agent's prompt, and determined what an ideal pre-constructed prompt looks like when forking off **two or more** agents. The analysis is written to:

`sase/repos/research/202607/multi_agent_fork_prompt_design.md`

**Key findings:**
- **Today's single-agent fork** runs three hidden steps (resolve name→chat path, load via `load_chat_for_resume`, inject) wrapped in a `%xprompts_enabled:false … :true` envelope. Critically, `load_chat_for_resume` emits **unlabeled** `**User:**`/`**Assistant:**` turns with zero attribution — naively concatenating two transcripts would blur them together.
- **The ideal N≥2 prompt** adds three things and reuses everything else: a preamble naming the situation and giving a conflict-resolution rule, a `## Conversation K of N — agent \`name\`` header per source for provenance/boundaries, ordered as the user listed them. N=1 stays byte-identical, so the change is purely additive.
- **Recommended solution:** extend `#fork` in place (not a separate `#merge`), keep one `type: agent` input, make `#fork:a,b` the canonical multi form (works with no schema change since the colon grammar delivers `"a,b"` as one value). Four localized edits: `agent_chat_from_name.py` (resolve list), `fork.yml` `load_history` (labeled block), the comma-aware `_RESUME_REF_RE` in `chat.py` (correctness-critical for re-forking), and `names/_resume.py` (name allocation / implicit waits).

The commit finalizer flagged the new markdown file; I committed it to the research sidecar repo as `docs(research): add multi-agent fork prompt design analysis`. Since only a research-doc file was created (no source changes in the sase workspace), `just check` doesn't apply.
