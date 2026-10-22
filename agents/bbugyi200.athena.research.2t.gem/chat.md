# Chat History - ace-run (research.2t.gem)

- **TIMESTAMP:** 2026-09-27 16:53:23 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2t.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_164135.md`

## Prompt

%id(gem, clan=research.2t)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2t.cdx`, `research.2t.cld`, `research.2t.grk`, `research.2t.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to integrate
the `sase tool` command into the "Agents" tab and maybe other parts of the TUI too, but
I'm not sure where to start. I was thinking of maybe adding a new card to the "Tools"
deck for this and adding a little hammer icon with a count to agent nodes that made tool
calls, but I'm not confident that either of these are great integrations.

Can you do some research with the goal of helping me decide the best way to implement
this? Think hard about what the best possible UX design for the `sase tool` command is.
End your analysis with a recommended solution. 
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

# Research Report: UX Design & Architectural Integration of `sase tool` into the SASE TUI

**Researcher**: `research.2t.gem`  
**Report Artifact**: [`research:202609/sase_tool_tui_ux_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_49/sase/repos/research/202609/sase_tool_tui_ux_design__gem.md)  
**Registered Artifact Ref**: `file:explicit:c0b7ffb05f57fc367e46022f`  

---

## 1. Executive Summary & Validation of User Intuition

You raised two specific ideas for integrating `sase tool` into the TUI:
1. *Adding a little hammer icon with a count to agent nodes that made tool calls.*
2. *Adding a new card to the existing "Tools" deck on the Agents tab.*

**Your hesitation and lack of confidence in both ideas are completely justified.** Our investigation into the codebase, TUI architecture, and the `sase tool` subsystem shows why both ideas suffer from fundamental design and semantic flaws:

1. **The Semantic Collision of "Tool":** There is an acute semantic clash between:
   - **LLM Tool Calling** (provider function calling like `view_file`, `replace_file_content`, `run_command` recorded in `tool_calls.jsonl`, rendered in the Agents tab's `Tools` deck with glyph `λ`).
   - **SASE Named Tools** (project-level deterministic build/test/lint commands like `just check` defined under `tools:` in `sase/sase.yml`, which record `ToolRun` entries, multi-stage timelines, failure triage items, and cryptographic verdict receipts).
2. **The "Hammer Icon with a Count" Problem:**
   - If the hammer counts LLM calls (`view_file`, etc.), almost every single agent makes dozens or hundreds of calls (`🔨 42`, `🔨 110`). It becomes visual noise across an already information-dense node panel (`_agent_list_render_agent.py`) while conveying zero actionable signal.
   - If the hammer counts `ToolRun` executions (`🔨 1`), a raw count conveys **no outcome**. The user doesn't know if verification passed, failed, introduced new regressions, or is still running. Furthermore, monitor turns (`<session>--mon`) already have their own node in the tree.
   - Non-agent tool runs (runs executed directly by a developer in bash via `sase tool run check`, or runs triggered by background schedulers) have **no agent node at all** and would be completely invisible.
3. **The "Card in the Tools Deck" Problem:**
   - Agent Data Decks are strictly **node-local** to the currently selected agent. Confining `sase tool` to a deck card makes it invisible when viewing agents that performed no verification, hides all human/CI/scheduler runs, and turns an active interactive control plane (run, stop, follow logs, triage) into a passive, read-only text scroll.
   - Having a deck containing both `LLM Calls` and `Tool Runs` severely confuses users about which kind of "tool" they are looking at.

---

## 2. The Recommended Solution: The Three-Pillar Tool UX

We recommend decoupling project-level tool execution from agent-level inspection, creating a unified experience across three distinct pillars:

```
                                THREE-PILLAR TOOL UX
                                
   ┌───────────────────────┐   ┌───────────────────────┐   ┌───────────────────────┐
   │       PILLAR 1        │   │       PILLAR 2        │   │       PILLAR 3        │
   │   GLOBAL TOOL HUB     │   │   AGENTS TAB CONTEXT  │   │  INTERACTIVE CONTROL  │
   ├───────────────────────┤   ├───────────────────────┤   ├───────────────────────┤
   │ • Dedicated Tools Hub │   │ • Verification Status │   │ • Quick Runner Palette│
   │   (ToolsPane modal /  │   │   Chips on agent rows │   │   (hotkey 'T' or ';') │
   │   candidate 4th tab)  │   │   ([✓ check], [✗])    │   │ • Live stage progress │
   │ • Catalog + Ledger +  │   │ • Verification Card   │   │ • Stop/Wait controls  │
   │   Stage Inspector +   │   │   in FINAL deck (⊛)   │   │ • 1-click jump from   │
   │   Triage Signatures   │   │ • Rebrand λ to "Calls"│   │   failure to bead/code│
   └───────────────────────┘   └───────────────────────┘   └───────────────────────┘
```

---

### Pillar 1: The Global Tool Hub (`ToolsPane`)

`sase tool` needs a first-class project-wide surface. We recommend implementing `ToolsPane`:
- **Access**: Global keybinding `g t` (goto tools), `:` command line (`:tool`), and command palette (`;tool runs`, `;tool catalog`).
- **Layout (Master-Detail)**:
  - **Upper Left (Catalog)**: Project named tools from `sase/sase.yml` (`check`, `test`, `install`, `check-full`, `test-visual`). Displays LAST status chip (`✓ pass`, `✗ fail/1`, `⟳ run`), TYPICAL runtime (e.g. `4m 13s (n=30)`), and covering receipt status. One-key execution: `r` to run in background (`-H`), `R` to run with extra arguments.
  - **Lower Left (Ledger)**: Recent recorded `ToolRun`s with live status chips, duration, and owner (agent name, monitor ID, or CLI). Filterable by tool name, state (`running`, `failed`), or active project.
  - **Right Column (ToolRun Inspector)**:
    - **Stage Timeline**: Interactive breakdown of `run_silent` stages (`fmt`, `lint (ruff)`, `lint (mypy)`, `lint (symvision)`), showing per-stage elapsed time and progress bars.
    - **Failure Triage Table**: Grouped failure signatures classified as `[NEW]` (regressions), `[KNOWN]` (existing baseline), or `[FLAKY]`. Pressing `Enter` on a failure jumps directly to the offending file/line; pressing `b` opens `/sase_new_task` with pre-filled context.
    - **Retained Log Stream**: High-performance stdout/stderr viewer with search (`,/`) and live follow mode (`F`).

---

### Pillar 2: Contextual Agents Tab Integration

On the Agents tab, integrate verification where it delivers true diagnostic value:

1. **Verification Status Chips on Agent Rows (Node Panel)**:
   - Instead of a generic hammer count, display an **Authoritative Verification Chip** *only* when the agent or its monitor turns executed verification:
     - `[✓ check]` (green): Tool run succeeded or minted a covering verdict receipt.
     - `[~ check]` (yellow): Completed with KNOWN baseline failures only (`no_new_failures`).
     - `[✗ check: 2 new]` (red): Failed with new regressions (`new_failures`).
     - `[⟳ check: symvision]` (cyan): Actively executing in the background, showing current stage.
   - Agents with no verification display no badge, preserving visual cleanliness.
2. **Rebrand the `TOOLS` Deck to "LLM CALLS"**:
   - In `spec.py`, rename `DeckId.TOOLS` display name to `CALLS` or `LLM CALLS` (keeping glyph `λ`). This cleanly isolates model function calling.
3. **Add a Verification Card to the `FINAL` Deck**:
   - The `FINAL` deck (`DeckId.FINAL`, glyph `⊛`, *"how this node's turns landed"*) is already the designated home for turn landing and completion.
   - Place a dedicated **Verification Card** here showing the covering receipt, the exact `ToolRun` id, stage breakdown, and triage verdict. Pressing `Enter` jumps directly to the full Tool Hub.

---

### Pillar 3: Interactive Execution & Fast Runner Flow

- **Quick Runner Palette**: Pressing `t` (in normal mode) or `;tool run` opens a lightweight centered popup listing catalog tools (`check`, `test`). Pressing `Enter` fires a background execution (`-H`) with zero disruption to active agent browsing.
- **Settlement Notifications**: When a background run completes, a non-intrusive toast reports the outcome: `ToolRun 9443436 (check) succeeded (4m 12s) · Receipt minted`.

---

## 3. Implementation Phasing

1. **Phase 1 (Data Models & Bridge)**: Create `src/sase/ace/tui/models/tool_runs.py` wrapping `sase.core.tool_run` and `sase.tool.query` with asynchronous workers.
2. **Phase 2 (Agents Tab Badges & Deck Clarification)**:
   - Append verification outcome chips in `_agent_list_render_agent.py`.
   - Rebrand `TOOLS` deck display name to `CALLS`.
   - Add `VerificationCard` to the `FINAL` deck.
3. **Phase 3 (Global Tools Hub & Quick Runner)**:
   - Implement `ToolsPane` in `src/sase/ace/tui/modals/tools_pane.py` (registered in Admin Center / `g t`).
   - Implement `ToolRunnerModal` for quick background launches.

---

The complete research report with full wireframes, architectural analysis, and code touchpoints has been saved and registered as a durable artifact at:  
`sase/repos/research/202609/sase_tool_tui_ux_design__gem.md` (`file:explicit:c0b7ffb05f57fc367e46022f`).
