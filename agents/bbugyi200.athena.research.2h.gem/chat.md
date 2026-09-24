# Chat History - ace-run (research.2h.gem)

- **TIMESTAMP:** 2026-09-24 10:00:31 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2h.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260924_093628.md`

## Prompt

%id(gem, clan=research.2h)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.2h.cld`, `research.2h.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I think I want to make the command
pallette trigger via the `;` keymap only and use the `:` keymap to trigger a new
"command-mode" panel that allows users to run `sase` commands directly from the TUI.

- The goal would be to give the user much better completion than the command-line ever
  could without ever needing to leave the TUI.
- We should default to showing the output of the command inline in the command-mode
  panel, but the user should also be able to leave the command-mode panel since the
  command should be run as a proc (which can be viewed on the "Procs" tab of the "SASE
  Admin Center" panel).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

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

# Research Report: SASE TUI Command Mode (`:`) and Command Palette Decoupling (`;`)

**Author:** Researcher Gem (`research.2h.gem`)  
**Report File:** [`tui_command_mode_design_and_critique__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/sase/repos/research/202609/tui_command_mode_design_and_critique__gem.md)  
**Registered Artifact:** `research:202609/tui_command_mode_design_and_critique__gem.md` (`file:explicit:de1e7a29a02448e5961f9b65`)

---

## Executive Summary & Core Verdict

The proposal to decouple the Command Palette (`;`) from a new in-TUI Command Mode (`:`) is **strongly recommended**, as it solves a major ergonomics gap in SASE while naturally aligning with Vim/Neovim modal conventions. 

Currently, users must frequently suspend or exit the TUI to run quick inspections (`sase bead show`, `sase patch list`, `sase doctor`, `sase usage`). Bringing `sase` command execution into the TUI with supervised proc guarantees transforms the TUI into a complete, self-contained development environment.

However, an in-depth investigation of the SASE architecture revealed **three critical technical hazards** that require adjustments to the user's initial plan:
1. **The Headless Proc vs. Interactive Stdin Trap:** SASE procs run detached with `stdin=DEVNULL`. Any command expecting an interactive terminal (such as `$EDITOR` during `sase patch reword`, interactive agent prompts, or `[y/N]` confirmations) will immediately fail or hang if naively dispatched as a headless proc.
2. **The 1.68-Second Argparse Import Tax:** Benchmark measurements showed that building the `CompletionSpec` from scratch takes **~1,680ms** because importing 63 subcommands imports nearly the entire codebase. A pre-compiled or background-loaded grammar cache is mandatory to achieve < 10ms modal popup latency.
3. **Command Weight Disparity:** Running micro-queries (e.g., `--version`, `--help`) as durable procs creates unnecessary disk churn in `procs.jsonl` and adds 50–80ms of supervisor bootstrap overhead.

---

## 1. Critique of the Proposed Plan

### 1.1 The Keybinding Split (`;` vs. `:`)
- **Evaluation:** Pure win. In `src/sase/default_config.yml`, `open_command_palette` was previously bound to `"colon,semicolon"`. Binding `;` to internal TUI actions (navigation, toggles, panel zooming) and `:` to CLI command execution maps directly to modern modal editor setups (e.g. Neovim Telescope on `;` and Ex-command mode on `:`).
- **Impact:** Clean separation between **TUI Action Dispatch** and **System Subprocess Invocations**.

### 1.2 Proc Execution & Admin Center Synergy
- **Evaluation:** Excellent architectural reuse. By submitting commands via SASE's `submit_proc_request`:
  - Output is durably streamed to `~/.sase/procs/logs/<proc_id>.log` and recorded in `procs.jsonl`.
  - Commands automatically appear on the SASE Admin Center **Procs** tab (`#` then `4`).
  - Active procs automatically light up the blue proc gear indicator in the TUI top bar (`ProcIndicator`).
  - The UI thread never blocks during heavy command execution.

### 1.3 The Interactive Command Hazard
- Commands in SASE's proc supervisor run detached under `DEVNULL`.
- **Recommendation:** The runner must parse the command before dispatch. If non-interactive flags exist (e.g. `--non-interactive`, `--yes`, `--json`), inject them automatically. If a strictly interactive command is requested (like `$EDITOR`), execute it via Textual's `with app.suspend():` for terminal takeover rather than spawning a headless proc.

---

## 2. In-TUI Completion: Why It Outperforms Shell Completion

Shell completion (Bash, Zsh, Fish) is constrained by terminal protocols and cannot access live application state. In-TUI Command Mode provides:
1. **Zero-Latency In-Memory Lookups (< 1ms):** No subprocess fork/exec on `Tab`.
2. **Hyper-Contextual Awareness:**
   - On the Artifacts tab inspecting patch `feat-auth`, typing `:patch ` prioritizes `feat-auth` with a `[Current Patch]` badge.
   - If an active bead `sase-88` is selected, `:bead show ` offers `sase-88` first.
   - Auto-scopes repos and workspaces to the active project.
3. **Dual-Pane Completion Card:** Left pane displays fuzzy-matched candidates with type chips; right pane displays rich markdown documentation, argument types, and examples.
4. **Live Signature Breadcrumbs:** Displays `sase bead show <id> [--json] [--no-notes]` above the input, highlighting the active argument as the cursor moves.
5. **Real-time Syntax Highlighting & Linting:** Colors commands, subcommands, and flags; flags unknown options with red underline before Enter is pressed.

---

## 3. UI & Visual Design ("Intuitive, Reliable, Beautiful")

### 3.1 Recommended Container: Top-Weighted Floating Console Modal (`CommandModeModal`)
Rather than mounting a bottom dock (which causes screen reflows and widget jitter across background tabs), use a dedicated `ModalScreen`:
- **Geometry:** Horizontally centered, top-weighted (`margin-top: 10%`, `width: 84%`, `max-width: 120`, `height: auto`, `max-height: 80%`).
- **Styling:** Double border in SASE primary teal (`#00D7AF`), dark translucent backdrop, and crisp badge typography.

### 3.2 State Flow
1. **Input State (`STATE_COMPLETING`):**
   - Header with `[READY]` chip.
   - Input line with fixed `sase ❯ ` sigil.
   - Live signature breadcrumb bar.
   - Dual-pane completion card (Candidates + Docstring Preview).
2. **Execution State (`STATE_STREAMING`):**
   - Header switches to `⠋ RUNNING (proc: p-8f3a)`.
   - Completion card flips to the **Output Viewport** with auto-scrolling live stdout/stderr.
   - Action footer: `[Esc] Background (Leave)   [K] Kill Proc   [y] Copy Output   [#4] Procs`.
3. **Backgrounding & Leaving:**
   - Pressing `Esc` or `q` immediately closes the modal.
   - The proc continues running under its detached supervisor.
   - A toast notification confirms: `Proc #proc-id running in background. View with # then 4.`
   - When finished, a completion toast records success or failure.

---

## 4. Key Adjustments to Requirements

1. **Implicit / Optional `sase` Prefix:** Do not force the user to type `sase`. Typing `:bead show sase-88` is identical to `:sase bead show sase-88`. The input prompt displays `sase ❯ ` as a fixed sigil.
2. **Built-in Ex-Command Shortcuts:** Intercept standard single-word Ex-commands before falling through to CLI execution:
   - `:q` $\rightarrow$ Exit TUI.
   - `:w` $\rightarrow$ Flush dirty state / stash prompt.
   - `:procs` $\rightarrow$ Jump directly to Admin Center Procs tab (`#4`).
   - `:help` $\rightarrow$ Open TUI help modal (`?`).
   - `:last` $\rightarrow$ Re-attach to the output of the most recent command.
3. **Interactive Command Safety:** Cleanly intercept interactive commands requiring a TTY and run them inside `with app.suspend():` rather than letting them hang under `DEVNULL`.
4. **Grammar Cache Warmup:** Persist a pre-serialized `completion_spec.json` (451 KB) and warm it up asynchronously on TUI startup, dropping cold start latency from 1,680ms to < 10ms.
5. **Quick Re-attach (`:last` / `Ctrl+O`):** Allow instant re-opening of a running background command's output without forcing the user to navigate through `#` then `4`.

---

## 5. Implementation Roadmap

- **Phase 1: Keymap Decoupling:** Update `default_config.yml`, `app_keymaps.py`, metadata, and help modals to bind `;` to `open_command_palette` and `:` to `open_command_mode`.
- **Phase 2: Completion Spec Caching:** Implement serialization/deserialization for `CompletionSpec` with version-based invalidation.
- **Phase 3: `CommandModeModal` Textual UI:** Build the input row, dual-pane completion card, and signature renderer.
- **Phase 4: Proc Runner & Streaming:** Wire `submit_proc_request(..., origin="command-mode")` to tail `proc.log_path` into the Textual output viewer.
- **Phase 5: Ex-Commands & Admin Center Polish:** Add `:q`, `:procs`, `:last` handlers and link to Admin Center.

---

### Artifact Verification
The complete research report has been committed and registered as an audited artifact:
```bash
sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/sase/repos/research/202609/tui_command_mode_design_and_critique__gem.md" -l "research:202609/tui_command_mode_design_and_critique__gem.md"
# Output ref: file:explicit:de1e7a29a02448e5961f9b65
```
A finalizer declaration manifest has been submitted and accepted via `sase final submit`.
