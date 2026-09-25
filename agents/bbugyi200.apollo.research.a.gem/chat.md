# Chat History - ace-run (research.a.gem)

- **TIMESTAMP:** 2026-09-25 16:36:09 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.a.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_162656.md`

## Prompt

%id(gem, clan=research.a)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.a.cdx`, `research.a.cld`, `research.a.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Sase's
finalizers are a critical part of a sase agent's lifecycle yet they are not represented
on the "Agents" tab in any way. I want to add excellent (and beautiful) support to this
tab for finalizers.

Can you do some research with the goal of helping me decide the best way to implement
this? Review the old agents_tab_finalizer_panel.md file in the research sidecar repo for
context and inspiration before performing your own research. Make sure to think hard
about what role decks, cards, and/or card blocks (card blocks are an upcoming
feature--see the agent_data_card_blocks.md file in the research sidecar repo for
context) should play (if any) in providing the user with an excellent way to visualize
and troubleshoot their own finalizers (I have several plans for new finalizers so make
sure you don't overfit this use-case to the builtin `commit` finalizer) . End your
analysis with a recommended solution. 
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

# Research Report: Agents Tab Finalizer Observability via Decks, Cards, and Card Blocks

**Researcher:** `research.a.gem` (gem)  
**Date:** 2026-09-25  
**Artifact ID:** `explicit:935fc614952e38e72a4791f6`  
**Artifact Reference:** `file:explicit:935fc614952e38e72a4791f6`  
**Stored Snapshot Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260925162656/agents_tab_finalizers_card_blocks_architecture__gem-315e37ff1ac1.md`  
**Research Repo Report:** [`research:202609/agents_tab_finalizers_card_blocks_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202609/agents_tab_finalizers_card_blocks_architecture__gem.md)

---

## Executive Summary & Recommended Solution

SASE's execution model draws a fundamental distinction between the agent turn (the LLM's non-deterministic deliberation and tool calls) and completion (deterministic host-owned finalizers executing verification, repository mutation, and dispatch per [`decisions:host-owned-completion`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/memory/decisions/host_owned_completion.md)).

Currently, the "Agents" tab displays **zero** representation of finalizers. For up to several minutes (23.9% of historical runs exceed 30 seconds; 13.4% exceed 5 minutes), the agent row remains ambiguously on `RUNNING` while the host executes pre-commit hooks, conflict repairs, or test suites. Furthermore, when failures occur (6.7% of runs across 16+ distinct diagnostic codes), the agent row falls silent.

Evaluating the problem against SASE's three-tier visual hierarchy (**Deck → Card → Card Blocks**):

1. **Decks:** **Do NOT create a 4th Deck (`DeckId.FINALIZERS`).**  
   Decks (`MAIN`, `FILES`, `TOOLS`) represent orthogonal modalities of the entire agent session (discourse, workspace diffs, tool telemetry) that exist continuously. A finalizer is a lifecycle phase occurring only at completion. Adding a 4th deck hides failures in single-panel mode (out-of-sight hazard) and breaks conversational context.

2. **Cards:** **Add a dedicated `Finalizers` Card to the `MAIN` Deck (`context`, `reply`, `finalizers`).**  
   - Visible in the `MAIN` title strip: `◆ MAIN ┃ Context │ Reply │ Finalizers` (omitted if no finalizers planned).
   - In `SPREAD` mode (default for concise documents), the agent run reads as a complete chronological narrative: **Prompt (`Context`) → Work (`Reply`) → Verification & Output (`Finalizers`)**.
   - In `PAGED` mode, switching cards is a single `Tab` or click, giving finalizers the full height and width needed for deep diagnostic inspection without fighting the prompt or reply for vertical space.
   - Active status pill in the card tab: `Finalizers ⛭` (running/yellow), `Finalizers ✓` (green), or `Finalizers ✗` (accent red), providing instant discovery.

3. **Card Blocks:** **Model each Finalizer Instance as a Card Block within the `Finalizers` Card.**  
   - An agent run executes a pipeline of finalizer instances (`commit`, `check`, `pr`, `notify`). Each instance becomes a non-nesting **Card Block** (`CardBlock`).
   - A dedicated **Finalizer BlockRail** renders at the top of the card:  
     `[ 1 commit ✓ ]  [ 2 lint ✓ ]  [ 3 test ✗ ]  [ 4 pr ○ ]`  
     matching the session timeline language (numbers, labels, glyphs, status colors).
   - **Triage-First Navigation (`[` / `]`):** When entering the `Finalizers` card on failure, the view **lands automatically on the first failed block** (`3 test ✗`), bypassing successful steps. The user immediately sees the failure reason, exit code, and error tail. Pressing `[` steps backward to inspect earlier successes; pressing `]` inspects skipped/blocked steps.
   - **Block Spread vs Block Paged:** If finalizer outputs are short (e.g. only `commit`), blocks spread inline. If any instance emits lengthy output (e.g. a failing test suite), the card pages the blocks one instance at a time with a seek-based log tail.

4. **Row & Header Observability:**  
   - Agent row status transitions: `RUNNING` → `FINALIZING` (with elapsed time ticker).
   - Agent row chip: distinct `⛭` chip on non-success only (silent on 93% success).
   - Detail Header Summary: a dedicated `finalizers` lane (`Finalizers: commit (7a2b9c) ✓ · test ✗`), ensuring status is immediately visible even when the user is focused on `Reply` or `FILES`.

---

## Visual Design of the `Finalizers` Card

```text
╭─ ◆ MAIN ───────────────────────────────────────────────────────────── [1.5x] ─╮
│ Context │ Reply │ Finalizers ✗                                                │
│                                                                               │
│ ┌─ RAIL ────────────────────────────────────────────────────────────────────┐ │
│ │  1 commit ✓ 1.4s  │  2 lint ✓ 3.1s  │ [3 test ✗ 42s] │  4 pr ○ (blocked)  │ │
│ └───────────────────────────────────────────────────────────────────────────┘ │
│                                                                               │
│ ── INSTANCE: test (builtin@command) ────────────────────── ATTEMPT 1/1 ────── │
│ Status:      FAILED (exit code 101)                Duration: 42.1s            │
│ Command:     pytest -q tests/unit tests/fast                                  │
│ Trigger:     on_success                            After:    [commit, lint]   │
│                                                                               │
│ ── DIAGNOSTICS ────────────────────────────────────────────────────────────── │
│ ✖ test_failed: 2 tests failed, 48 passed, 1 error                             │
│   tests/unit/test_tokens.py:84: AssertionError: expected 200, got 401         │
│   tests/fast/test_crypto.py:12: ModuleNotFoundError: No module named 'curve'  │
│                                                                               │
│ ── TERMINAL OUTPUT (tail 16 lines) ────────────────────────── [E: Open Log] ─ │
│ _________________________________ test_token_auth __________________________ │
│     def test_token_auth():                                                    │
│         client = Client()                                                     │
│ >       response = client.get("/auth")                                        │
│ E       assert response.status_code == 200                                   │
│ E       AssertionError: assert 401 == 200                                     │
│                                                                               │
│ tests/unit/test_tokens.py:84: AssertionError                                  │
│ =========================== short test summary info ========================== │
│ FAILED tests/unit/test_tokens.py::test_token_auth                             │
│ ERROR tests/fast/test_crypto.py - ModuleNotFoundError: No module named 'curve' │
│ !!!!!!!!!!!!!!!!!!!!!!!!!!! Interrupted: 1 error !!!!!!!!!!!!!!!!!!!!!!!!!!!!! │
│ ==================== 2 failed, 48 passed, 1 error in 41.82s ================= │
│                                                                               │
│ [ [ / ] ] Select Block  ·  [E] Open Full Log  ·  [V] Live Modal  ·  [Tab] Cards│
╰───────────────────────────────────────────────────────────────────────────────╯
```

---

## Multi-Instance Extensibility (Beyond `builtin@commit`)

To prevent overfitting to git commits, the snapshot model supports three distinct finalizer categories:

1. **VCS / Mutation Finalizers (`builtin@commit`):**  
   Displays commit SHA, target branch, unpushed count, stitch status, pre-commit hook results, and multi-attempt conflict repair tracking (`commit_repair.py`).
2. **Verification & Command Finalizers (`builtin@command`):**  
   Executes linters, type checkers, test runners, or benchmarks (`ruff`, `cargo test`, `pytest`). Tracks process execution, exit codes, scoped assertion errors, and formatted ANSI stderr/stdout logs.
3. **Integration & Notification Finalizers (`plugin@github`, `plugin@telegram`):**  
   Publishes pull requests, posts PR comments, and dispatches chat notifications. Tracks external API response status, created URLs, and delivery confirmation.

---

## Performance, Calmness, and Rust-Core Precedence

- **Rust Core Reconciliation (`FinalizerRunSnapshotWire`):**  
  In accordance with [`decisions:rust-core-required`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/memory/decisions/rust_core_required.md), reconciliation of `finalizer_plan.json`, `progress.jsonl`, `final_context.json`, and `finalizer_result.json` lives in `sase-core/crates/sase_core/src/finalizer/`.
- **Source Precedence:**  
  1. Authenticated plan is authoritative for instance selection, dependencies, and policies.
  2. Terminal result dominates everything once recorded.
  3. Journal (`progress.jsonl`) is authoritative for runtime phase only while the runner process is alive.
  4. Dead runner + no terminal result = `interrupted` (eliminating forever-spinning zombie states).
- **The 5-Second Calmness Gate:**  
  No live subprocess tail renders until a finalizer instance has run for ≥ 5.0 seconds. Fast 2-second finalizers transition cleanly from `● → ✓` without UI flicker or CPU churn.
- **Safety Ceilings:**  
  Enforces a 1 MiB pre-parse ceiling and render-time deduplication to prevent freeze issues from pathological logs (such as the 3.32 MB diagnostic result identified in historical data).

---

## Delivery Plan

Implementation is split into four clean increments gated behind a beta flag (`sase flag new ace_finalizer_cards`):
1. **Phase 1: Foundational Observability:** `progress.jsonl` lifecycle journal, additive `finalizers` field in `agent_meta.json`, `FINALIZING` status word, `⛭` row chip, and detail header summary lane.
2. **Phase 2: `Finalizers` Card & Card Blocks View:** `FinalizerRunSnapshotWire` in `sase-core`, `Finalizers` card in `MAIN`, `CardBlock` wrapping per instance, `BlockRail`, `[` / `]` navigation, and triage landing.
3. **Phase 3: Live Streaming & Logs:** Subprocess `live_sink`, 5-second calmness gate, seek-based tail reading, and editor (`E`) / modal (`V`) log inspection.
4. **Phase 4: Polish & Documentation:** Diagnostic deduplication, TUI performance verification (`bench_tui_jk.py`), flag deprecation, and documentation updates.

The complete report is registered and available at [`research:202609/agents_tab_finalizers_card_blocks_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202609/agents_tab_finalizers_card_blocks_architecture__gem.md).
