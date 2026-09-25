# Chat History - ace-run (research.9.gem)

- **TIMESTAMP:** 2026-09-25 14:03:26 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.9.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_135331.md`

## Prompt

%id(gem, clan=research.9)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.9.cdx`, `research.9.cld`, `research.9.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to rename the `%proc` directive to
`%tool` and add some features to it to better support the `sase tool` command (see the
sase_tool_epic_roadmap.md file in the research sidecar repo for context).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? End your analysis with a recommended solution. 
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

# Research Report & Architecture Critique: Renaming `%proc` to `%tool` for `sase tool` Support

**Author:** Researcher `gem` (Swarm Member)  
**Report Artifact:** `research:202609/proc_directive_to_tool_rename__gem.md`  
**Stored Artifact Ref:** `file:explicit:0d1ef33edf75465ab6b86722`  
**Local Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202609/proc_directive_to_tool_rename__gem.md`

---

## Executive Summary & Direct Answer

You asked:
1. *Is renaming `%proc` to `%tool` a good idea?*
2. *Would I take a different approach?*
3. *What is the best way to implement this and what is the recommended solution?*

### The Verdict Up Front
**No, an in-place rename of `%proc` to `%tool` is not a good idea.** It represents a **conceptual category error** that conflates an *execution mechanism* (an isolated, supervised OS process shell) with a *domain entity* (a project-governed named tool with defined inputs, stages, and ledger records).

### The Recommended Solution: Orthogonal Two-Tier Directives
Instead of renaming `%proc`, adopt a **Two-Tier Architecture**:
1. **Retain `%proc`** as the low-level execution primitive for arbitrary Bash/Python scripts (`%proc:: \n ```bash ... ``` `). This maintains the clean symmetry established in `sase-s6` (`LaunchUnit::ProcUnit` vs `LaunchUnit::AgentUnit`).
2. **Introduce a dedicated, first-class `%tool` directive** (`%tool(check)`, `%tool(test, args=["..."])`, `%tool(check, keep_going=true)`) that directly targets the `sase tool` catalog in `sase/sase.yml`, compiles to a new `LaunchUnit::ToolUnit`, validates tool existence statically at plan expansion time, and dispatches directly into the `ToolRun` recording engine.

---

## 1. Critique: Why an In-Place Rename Breaks Down

### A. Mechanism vs. Entity (The Category Error)
- **`proc` is a Mechanism:** It defines *how* a unit executes: as a supervised OS process (`proc-shell`, `~/.sase/procs/`) rather than an LLM agent. It accepts arbitrary, multi-line Bash or Python scripts.
- **`tool` is an Entity:** It defines *what* operation is performed: a repository-governed task defined in `sase/sase.yml` (`check`, `test`, `install`) with stage protocols (`run_silent`), dirty input tracking, and an immutable entry in the machine-local `ToolRun` SQLite ledger (~180-day retention).
- **The Dilemma:** If `%proc` is renamed to `%tool`:
  - What happens when a user runs an arbitrary 5-line cleanup script: `%tool:: \n ```bash\nrm -rf /tmp/scratch\n``` `?
  - If that script is recorded in the `ToolRun` ledger, it pollutes the 180-day audit store with noisy, non-repeatable ad-hoc runs.
  - If it is *not* recorded, why is it called `%tool`? Calling an unrecorded, generic script runner `%tool` breaks the semantic integrity of the `sase tool` command.

### B. The "Triple Tool" Vocabulary Collision
SASE recently resolved the collision between LLM function calling and CLI commands by renaming the TUI panel to **LLM Calls** (`src/sase/ace/tui/llm_calls/`).
Renaming `%proc` to `%tool` introduces a third conflicting meaning:
- To an LLM reading an xprompt: `%tool` looks like an LLM function declaration rather than a background batch unit.
- In the TUI: Stand-alone procs appear in the **Procs pane** (`sase proc`, `~/.sase/procs/`). Calling the directive `%tool` while the runtime record, lifecycle, and pane are all `proc` creates mental friction.

### C. Missed Opportunity: Static Catalog Validation
`%proc` is untyped procedural code: typos like `%proc("just chekc")` can only be discovered at runtime after acquiring a workspace lease.
In contrast, a true `%tool(check)` directive allows the Rust core (`sase-core`) to **statically validate** the tool name against `sase/sase.yml` during prompt expansion *before approval and before execution*. An in-place rename that retains arbitrary script bodies loses this capability.

---

## 2. Comparative Alternatives Matrix

| Dimension | Option 1: In-Place Rename (`%proc` -> `%tool`) | Option 2: Two-Tier (`%proc` + `%tool`) **[Recommended]** | Option 3: Unified Directive with Sub-Modes |
| :--- | :--- | :--- | :--- |
| **Separation of Concerns** | **Poor.** Conflates OS process with project tool. | **Pristine.** Generic script runner vs project tool. | **Fair.** Mixed semantics in one keyword. |
| **`ToolRun` Ledger Integrity**| **Poor.** Pollutes ledger with throwaway scripts. | **Pristine.** Only `%tool` records in `ToolRun`. | **Moderate.** Requires tagging ad-hoc runs. |
| **Static Catalog Validation** | **No.** Accepts arbitrary strings. | **Yes.** Validates against `sase.yml` at plan time. | **Partial.** Only when named syntax is used. |
| **LSP Autocomplete & DX** | **Weak.** Generic string suggestions. | **Outstanding.** Autocompletes tools (`check`, `test`). | **Complex.** Branching completions. |
| **Backward Compatibility** | **Breaking.** Churn across existing xprompts/docs. | **100% Non-breaking.** `%proc` unchanged. | **Partial.** Requires deprecation window. |
| **Roadmap Alignment (E1–E8)**| **Awkward.** Stuffing flags into script blocks. | **Native.** Designed specifically for tool flags. | **Moderate.** Options apply conditionally. |

---

## 3. Best Way to Implement: The Dedicated `%tool` Directive

### Syntax & Ergonomics

1. **Named Project Tool:**
   ```text
   %tool(check)
   %tool("check")
   ```
   Statically validated against `sase/sase.yml`. Inherits defined argv, stages, and input file tracking.

2. **Named Tool with Arguments (when permitted by `sase.yml`):**
   ```text
   %tool(test, args=["tests/test_tool_handler.py", "-k", "test_runs"])
   ```
   Rejected at plan expansion if `sase.yml` specifies `args: deny` for that tool.

3. **Stage & Hand-off Execution (Epics E1 & E2):**
   ```text
   %tool(check, timeout="15m", keep_going=true, handoff=true)
   ```
   - `handoff=true`: Automatically delegates to `sase tool run -H` (durable execution surviving agent completion).
   - `keep_going=true` (`-k`) / `fail_fast=true` (`-x`): Configures stage progression.

4. **Verification Receipts & Staged Reuse (Epic E4):**
   ```text
   %tool(check, reuse=true)
   ```
   Checks for a valid green verification receipt on an unchanged git tree. If present, settles instantly as `cached`.

5. **Capacity Admission & Queuing (Epic E7):**
   ```text
   %q(priority=10, weight=0.5)
   %tool(check-full)
   ```
   Participates in Rust `runner_capacity` tool admission queue.

---

## 4. Technical Implementation Blueprint

### 1. Rust Core (`sase-core`)
- **`crates/sase_core/src/agent_launch/wires.rs`:** Add `ToolUnitWire` to `LaunchUnitPayloadWire`:
  ```rust
  pub enum LaunchUnitPayloadWire {
      Agent(AgentUnitWire),
      Proc(ProcUnitWire),
      Tool(ToolUnitWire),
  }
  ```
- **`crates/sase_core/src/agent_launch/plan_resolution.rs`:** 
  - Validate tool existence against the project's `sase.yml` tool catalog.
  - Enforce `args: deny` / `args: allow` policies.
- **`crates/sase_core/src/editor/wire.rs`:**
  - Dynamic LSP completion for `%tool(` offering live project tool names (`check`, `check-full`, `test`, `install`).

### 2. Python Runtime (`sase`)
- **`src/sase/xprompt/_directive_collect.py` & `_directive_extract.py`:**
  - Parse `%tool(...)` arguments (`name`, `args`, `timeout`, `keep_going`, `fail_fast`, `handoff`, `reuse`).
  - Explicitly reject code fences on `%tool` with an instructive diagnostic pointing to `%proc::`.
- **`src/sase/agent/launch_admission_runtime.py`:**
  - Dispatch admitted `ToolUnit` instances directly through `sase.tool.executor` (foreground) or `sase.tool.handoff_launch` (`-H`).
  - Link the created `ToolRun` id to the launch receipt and emit the typed artifact link `launch:<id>` -> `tool:<run-id>`.

---

## 5. Artifact & Deliverables Confirmation

1. **Research Report Written:**  
   [proc_directive_to_tool_rename__gem.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202609/proc_directive_to_tool_rename__gem.md)
2. **Snapshot Registered via SASE Artifact:**  
   - **Artifact ID:** `explicit:0d1ef33edf75465ab6b86722`  
   - **Label:** `research:202609/proc_directive_to_tool_rename__gem.md`  
   - **Stored Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260925135335/proc_directive_to_tool_rename__gem-0e91ce28ecb7.md`
3. **Turn Finalizer Declaration:**  
   Successfully declared and accepted via `sase final submit -` (`Accepted final declaration for: commit`).
