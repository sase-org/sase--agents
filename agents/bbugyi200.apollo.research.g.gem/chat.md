# Chat History - ace-run (research.g.gem)

- **TIMESTAMP:** 2026-09-26 15:57:50 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.g.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260926_154839.md`

## Prompt

%id(gem, clan=research.g)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.g.cdx`, `research.g.grk`, `research.g.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to make it
easier to set file hooks for artifact files by using a more robust and reliable approach
to matching artifact files.

- I was thinking that we could maybe achieve this by having the `#research` xprompt set
  an environment variable by default.
- We would need to support an override for this as well (e.g. by adding a new input
  argument to the `#research` xprompt) to not set this environment variable in some
  cases (we will need to set this override for all of the researcher agents that run
  before the lead researcher agent in the `#research_swarm` xprompt swarm, for example).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
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

# Research Report: Robust Artifact File Hook Matching & Critique of Environment Variable Approach

**Researcher ID:** `research.g.gem` (Gemini 3.8 Flash High)  
**Report File:** [`artifact_file_hook_matching__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202609/artifact_file_hook_matching__gem.md)  
**Artifact ID:** `explicit:291595f2c679add62082df8c` (`research:202609/artifact_file_hook_matching__gem.md`)

---

## 1. Executive Summary

The objective of this research is to evaluate whether using an environment variable set by the `#research` xprompt (with an opt-out override for peer swarm researchers) is an effective and robust mechanism for matching artifact deliverables in SASE file hooks.

### Core Findings & Critique
1. **The Core Motivation is Valid:** Today, file hooks like `research-highlights` (which runs `bob highlights create --include-id`) rely on a fragile pile of negative path globs (`!20*/*__*.md`, `!20*/*/*__*.md`) and negative agent name globs (`!research.*.cdx`, `!research.*.cld`, `!research.*.grk`, `!research.*.mus`, `!research.*.gem`). Adding a new provider to a research swarm forces manual updates to negative filter lists across the plugin and documentation. A more robust, positive matching approach is urgently needed.
2. **Ambient Environment Variables Are Architecturally Flawed for This Use Case:**
   - **Host Commit Finalization Boundary:** Commit-time file hooks (`producers: [commit, sdd, finalizer]`) execute in the host runner process *after* an agent turn finishes. Ambient environment variables set inside an agent process or during prompt expansion are not automatically replayed into host finalizers.
   - **XPrompt Format Constraints:** `#research` is currently a Markdown prompt part (`research.md`). Under SASE's frontmatter schema, Markdown prompt parts do not support an `environment:` mapping; only `.yml` workflows support `environment:`.
   - **`#research_swarm` Orchestration Gap:** In `#research_swarm`, the lead consolidator (`research.{@1}.final`) **does not invoke `#research`**—its instructions are defined inline. If `#research` is the sole mechanism setting the variable, the lead researcher will never have it set.
   - **Swarm Lead Artifact Creation Gap:** In `research_swarm.md`, the lead researcher only runs `sase artifact create` when `critique: true` (an opt-in flag defaulting to `false`). When `critique: false`, the lead never runs `sase artifact create` at all.
   - **Stored Path Hash Pollution:** If file hooks are triggered via `producer: artifact`, `sase` dispatches the durable content-addressed copy (`stored_path`, e.g., `report-d03c29462488.md`), which carries a 12-character SHA256 digest suffix. External tools like Bob embed this hash into Obsidian note marker IDs and filenames.

### Recommended Solution
Instead of ambient environment variables, SASE should adopt **first-class, declarative artifact intent**:
1. **Immediate Stabilization (Zero Core Changes):** Invert the brittle negative filtering in `provider.py` to positive role matching (`agent_name_globs: ["*.final", "!research.*.*"]`) and recursive path vetoes (`!20*/**/*__*.md`). Update `research_swarm.md` so the lead researcher unconditionally registers the consolidated report.
2. **Medium-Term Architectural Solution:** Extend `sase artifact create` with a `--tag <tag>` argument (e.g., `--tag report` or `--tag highlight`), add `tags` to `FileHookFilters`, and allow artifact file hooks to receive the clean source path rather than forcing the hashed stored path.

---

## 2. Detailed Technical Critique of the Proposed Approach

### Problem 1: Disconnect Between Agent Environment and Host Finalizers
In SASE, agents operate under the single-turn contract (`AGENTS.md` 1.1.4 and `decisions:single-turn-agents`). Agents do not commit repositories directly; host-owned finalizers commit at the end of the turn.
- `research-highlights` currently operates as a commit-time hook (`producers: [commit, sdd, finalizer]`).
- When the commit finalizer runs (`reconcile_commit_file_hooks()` in `src/sase/finalizers/commit_validation.py`), it executes in the host environment.
- It receives repo root, commit SHA, workspace directory, and agent identity. It does **not** inherit arbitrary environment variables set in the ephemeral agent subshell.
- Therefore, commit-time file hooks cannot filter on agent environment variables.

### Problem 2: Markdown Frontmatter Does Not Support `environment:`
The `#research` xprompt is defined at `src/sase_research_artifacts/xprompts/research.md`.
- SASE's `PromptFrontmatter` model (`src/sase/xprompt/prompt_frontmatter.py`) only parses:
  `("name", "description", "tags", "input", "xprompts", "skill", "snippet")`
- Only `.yml` workflows (`WorkflowModel` in `src/sase/xprompt/workflow_models.py`) support an `environment:` dictionary.
- Setting an environment variable would require converting `#research.md` into a multi-file or YAML workflow, or expanding the core frontmatter schema in Rust (`sase-core`).

### Problem 3: Orchestration Blindspots in `#research_swarm`
In `src/sase_research_artifacts/xprompts/research_swarm.md`:
1. Swarm researchers execute:
   `{{ prompt }} #research(suffix=cdx)`
   `{{ prompt }} #research(suffix=cld)`
   ...
2. The lead researcher executes an inline prompt segment (`%id:research.{@1}.final`):
   It performs directory setup, draft consolidation, and report synthesis directly. **It never calls `#research`**.
   If `#research` sets the environment variable, the lead researcher will never receive it unless `research_swarm.md` is also patched to inject the variable manually.
3. Furthermore, the lead researcher only executes `sase artifact create` conditionally:
   ```jinja
   {%- if critique %}
   5. After the write succeeds, register the consolidated report as a durable snapshot...
   {%- endif %}
   ```
   If `critique` is `false` (the default), the lead consolidator never registers an artifact deliverable.

### Problem 4: Content-Addressed Hash Suffix Pollution
In `src/sase/file_hooks/artifact.py`:
```python
def dispatch_artifact_file_hook_event(captured_source, stored_path, ...):
    event = CapturedFileEvent(
        abs_path=str(Path(stored_path).expanduser().resolve()),
        ...
    )
```
When an artifact file hook runs, `runner.py` passes `run['abs_path']` to the hook command. Because `abs_path` is `stored_path`, the filename passed to `bob highlights create --include-id` is `topic-d03c29462488.md`. Bob embeds `topic-d03c29462488` as the marker ID and outputs `topic-d03c29462488.pdf`, which was the exact reason `research-highlights` was restricted to commit-time hooks in the first place (`docs/configuration.md` lines 75–78).

---

## 3. Comparative Architecture Assessment

| Evaluation Dimension | 1. Env Var via XPrompt (Proposed) | 2. First-Class Artifact Tags (Recommended) | 3. Positive Path & Role Matching (Low-Hanging Fruit) |
| :--- | :--- | :--- | :--- |
| **Point of Enforcement** | Prompt template expansion / process environment | `sase artifact create --tag <tag>` | Hook provider filter specification |
| **Hook Compatibility** | Fails for commit hooks; ambient for artifact hooks | Native for artifact hooks; durable across turns | Works for commit hooks and artifact hooks |
| **Granularity** | Coarse (entire process environment) | Fine-grained (per individual deliverable) | Per-file / Per-commit |
| **Swarm Invariant Safety** | Leaks across peer segments unless overridden | Explicit (`--tag draft` vs `--tag report`) | Immune to adding new researcher model types |
| **Path Digest Pollution** | Unresolved for artifact hooks | Solved by exposing source path option | Solved (uses committed repo path) |
| **Maintenance Burden** | High (YAML workflow conversion, template logic) | Low (declarative CLI flag + filter field) | Minimal (regular expression / glob simplification) |

---

## 4. Recommended Implementation Strategy

### Step 1: Immediate Stabilization of `sase-research-artifacts`
1. **Unconditional Artifact Registration in Swarm:**
   In `src/sase_research_artifacts/xprompts/research_swarm.md`, make step 5 (consolidated report registration via `sase artifact create`) unconditional for the lead researcher, rather than guarded by `{%- if critique %}`.
2. **Invert Hook Matching to Positive Rules:**
   In `src/sase_research_artifacts/provider.py`, replace the negative enumeration of all researcher agent names with:
   ```python
   "filters": {
       "sidecars": ["research"],
       "producers": ["commit", "sdd", "finalizer"],
       "path_globs": [
           "20*/**/*.md",
           "!20*/**/*__*.md",  # Recursive veto: excludes all drafts and critique at any depth
           *_COMPANION_MARKDOWN_EXCLUDE_GLOBS,
       ],
       "agent_name_globs": [
           "*.final",          # Matches lead consolidator
           "!research.*.*",    # Rejects all other swarm clan members
       ],
       "ops": ["ADD"],
   }
   ```
   This ensures that adding new swarm researchers (e.g., `llama`, `deepseek`) never breaks the filter or leaks drafts into Highlights PDFs.

### Step 2: First-Class Artifact Tags in SASE Core (`sase`)
1. **Extend `sase artifact create`:**
   Add `-t, --tag` to `sase artifact create` (`src/sase/artifact_cli/create.py`), recording tags in `CapturedFileEvent`.
2. **Extend `FileHookFilters`:**
   Add `artifact_tags: tuple[str, ...] | None = None` to `FileHookFilters` in `src/sase/config/file_hooks.py`.
3. **Fix `abs_path` Dispatch:**
   In `src/sase/file_hooks/artifact.py`, allow the hook to receive `captured_source.abs_path` (the clean working-tree file) when `--move` was not passed.
4. **Declarative Hook Configuration:**
   Cut over `research-highlights` to:
   ```yaml
   filters:
     sidecars: [research]
     producers: [artifact]
     artifact_tags: [final-report]
   ```

---

## 5. Artifact Verification

The comprehensive research report has been written to disk and registered as a durable SASE artifact:

- **Absolute Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202609/artifact_file_hook_matching__gem.md`
- **Relative Path:** `202609/artifact_file_hook_matching__gem.md`
- **Artifact ID:** `explicit:291595f2c679add62082df8c`
- **Canonical Ref:** `file:explicit:291595f2c679add62082df8c`
- **Finalizer Declaration:** Submitted and accepted (`builtin@commit`).
