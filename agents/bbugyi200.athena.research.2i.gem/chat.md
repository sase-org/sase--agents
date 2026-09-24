# Chat History - ace-run (research.2i.gem)

- **TIMESTAMP:** 2026-09-24 14:42:41 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2i.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260924_142941.md`

## Prompt

%id(gem, clan=research.2i)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.2i.cdx`, `research.2i.cld`, `research.2i.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about moving
forward with the E3 and E4 epics described in the sase_tool_epic_roadmap.md file in the
research sidecar repo now that E2 (see the sase-17p epic bead) is almost complete. Can
you do some research with the goal of helping me determine if these epics are still
correct and appropriate? Should we make any changes to the epic? Flesh these epics out
enough that the epic landing criteria for both of these is crystal clear (the sase
agents that plan/implement/land these epics are likely to read this research). 
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

# Independent Research: Readiness, Architectural Adjustments, and Landing Criteria for `sase tool` Epics E3 and E4

**Researcher:** `research.2i.gem`  
**Date:** 2026-09-24  
**Workspace:** `sase_41` (host `apollo`, master `b85538009`, core pin `6d0d0e6d5c0e`)  
**Durable Artifact Reference:** `research:202609/sase_tool_e3_e4_readiness_and_landing_criteria__gem.md`  
**Artifact ID:** `explicit:51fa4d1ff4e3cd9ba4bbc83b`  
**File Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/sase/repos/research/202609/sase_tool_e3_e4_readiness_and_landing_criteria__gem.md`

---

## 1. Executive Summary & Core Verdict

### Are E3 and E4 Still Correct and Appropriate?
**Yes, unequivocally.** Both epics directly target the dominant sources of developer and agent waste on the platform today. An inspection of the live ToolRun SQLite ledger on host `apollo` (`~/.sase/tools/runs.sqlite`, 638 recorded runs) demonstrates:
- **490 out of 556 `check` runs failed (88.1% failure rate)**.
- **Over 71% of all stage failures were in cheap lint or formatting stages** (`lint (symvision)` failed 239 times; `lint (mypy)` failed 78 times; `lint (ruff)` failed 41 times) before heavy test execution.
- Master remains known-red (`sase-j0` budget check failures), forcing every agent running `check-full` to parse massive failure outputs and hand-author median 1,778-character baseline-difference essays to continuation agents.
- In SASE's multi-agent model, phase workers run `check` to verify a phase, and land agents re-run `check` on the *exact same tree*, duplicating 3.5–5 minutes of expensive execution per landed change. E4 eliminates this second run completely.

### Recommended Architectural Changes to E3 and E4
While the core goals remain sound, several key boundary refinements are needed to cleanly integrate with what landed in **E1.5** (`sase-16h: guarded recipes & monitor wrapping`) and **E2** (`sase-17p: durable handoff & settlement`):
1. **E3 must consume E2's `terminal_cause`:** Infrastructure and lifecycle aborts (`timeout`, `stopped`, `lost`, `crashed`) must be separated from deterministic verification failures (`terminal_cause: exited` with exit code > 0). A timeout or SIGKILL must never be misclassified as a "NEW" test failure.
2. **Pluggable vs Built-in Diagnostic Extractors:** E3 should provide built-in extractors for the standard toolchain (pytest, ruff, mypy, keep-sorted, symvision) and fall back gracefully to normalized exit diagnostics for arbitrary stages.
3. **Signature Stability:** Signatures must strip ephemeral workspace paths (`sase_<N>`), worker IDs, and shifting line numbers (using test node IDs and rule codes) to achieve true cross-workspace aggregation.
4. **`rerun RUN` ownership:** The roadmap mentioned `rerun` across both E3 and E4. **`sase tool rerun RUN` must be owned exclusively by E3** as an attempt-chain retry mechanism, while **E4 owns the `-R/--force` bypass flag** for cached receipts.
5. **E4 deterministic failure refusal safety:** E4's "unchanged-since-failure refusal" must refuse *only* when the prior failure was deterministic (`terminal_cause: exited` with exit code > 0), never when the prior run was lost, timed out, or interrupted.
6. **Host-Owned Landing Gate Compliance (Decision 7):** E4 receipts must satisfy the host-owned landing validator via a dedicated non-interactive query command (`sase tool receipt <tool>`). Agents must never bypass verification by fabricating receipt assertions.

### Recommended Sequencing: Strict Serial Execution ($E2 \rightarrow E3 \rightarrow E4$)
The roadmap originally suggested running `{E3, E4, E5}` in parallel. **We strongly recommend serial sequencing: E3 first, then E4.**
- Both epics require modifications to the shared Rust core (`crates/sase_core/src/tool_run/`). Running them concurrently risks core pin ratcheting collisions (identical to the issue documented in `sase-17p` Note #1).
- **E3 is read-only with respect to execution dispatch.** It carries low regression risk and immediately provides relief for the 88% failure rate and red master.
- **E4 alters execution dispatch** (short-circuiting runs on receipt match, running cheap stages first, refusing unchanged failures), building upon the stable diagnostic baseline established by E3.

---

## 2. Deep Dive: Epic E3 — Failure Triage (NEW vs KNOWN vs FLAKY)

### Scope and Architecture
1. **Infrastructure vs Verification Separation:**
   - If `terminal_cause != exited`: classified as `INFRASTRUCTURE` / `LIFECYCLE` failure; no signature parsing.
   - If `terminal_cause == exited` and `exit_code != 0`: parse diagnostics.
2. **Normalized Signature Invariants:**
   - Strip all ephemeral checkout prefixes (`sase_\d+/`).
   - Test failures: `test:<relpath>::<test_function>#<exception_class>` (node IDs are line-number invariant).
   - Linter failures: `lint:<linter_name>:<relpath>:<rule_or_code>[:<symbol>]`.
3. **Three-Tier Classification Engine:**
   - **KNOWN:** Matches signature from a run on `origin/master` or merge-base, or mapped to an active bead (e.g. `sase-j0`).
   - **FLAKY:** Matches entry in flake history or intermittent runs.
   - **NEW:** Introduced by local workspace changes.
4. **Structured Continuation Payloads:**
   - Updates `src/sase/monitor/followup_prompt.py` to embed a structured triage summary in continuation prompts, completely eliminating hand-written baseline prose.
5. **Attempt Chains via `rerun`:**
   - `sase tool rerun RUN`: re-executes `RUN` as attempt 2 (`parent_run_id = RUN`), ignoring receipts to verify if a failure was resolved or transient.

### Proposed Phases (~6 phases)
- `core-signatures`: Rust failure contracts, signature hashing, SQLite tables, PyO3 bindings, pin ratchet.
- `extractors`: Python diagnostic extractors for pytest, ruff, mypy, symvision, and generic exit codes.
- `classifier`: Three-tier classifier matching signatures against merge-base runs, task beads, and flake store.
- `cli-failures`: `sase tool failures [TOOL]` grouped views, `/sase_new_task` suggestions, and `sase tool rerun RUN`.
- `continuation-integration`: Wire structured triage into compact agent footers and monitor follow-up prompts.
- `acceptance-and-flags`: Prove end-to-end against multi-class failure fixture; remove `tool_failure_triage` beta flag.

---

## 3. Deep Dive: Epic E4 — Verification Receipts and Staged Reuse

### Scope and Architecture
1. **Dual Receipt Scopes:**
   - `scope: tree`: Shareable machine-wide across workspaces. Keyed by git tree hash, dirty diff, declared `inputs:`, toolchain versions, and allow-listed env vars. Used for `check`, `test`.
   - `scope: workspace`: Local to the workspace venv. Used for `install`.
2. **Pass-Only Minting:**
   - Only runs settling with `state: succeeded` mint receipts (with configurable TTL, e.g. 12h for `check`, 7d for `install`).
3. **Deterministic Unchanged-Since-Failure Refusal:**
   - Refuses re-execution if fingerprint matches an immediately prior run that failed with `terminal_cause: exited` ("Nothing changed since run <id> failed. Use -R to force").
   - Safety guard: never refuses if previous failure was an infra abort (`lost`, `timeout`, `crashed`).
4. **Cheap-Stages-First Protocol:**
   - Declared `cheap_stages: [lint, fmt]` run *inline* in the foreground before allocating heavy capacity or handing off to background monitors/procs.
   - If cheap stages fail: fail immediately in 15 seconds. If they pass: mint stage pass receipts and proceed.
5. **Host-Owned Landing Gate Integration (Decision 7):**
   - Host lander invokes `sase tool receipt <tool>` to verify receipts cryptographically before accepting landed changes without re-execution.

### Proposed Phases (~7 phases)
- `core-receipts`: Rust receipt wire contracts, SQLite `receipts` table, TTL algebra, PyO3 bindings, pin ratchet.
- `receipt-mint-and-query`: Minting on exit code 0; `sase tool receipt TOOL` CLI command.
- `run-reuse-and-force`: Integrate receipt lookup in `sase tool run`; implement `-R / --force` bypass flag.
- `unchanged-failure-refusal`: Deterministic refusal with explicit prior run citations and safety exemptions.
- `cheap-stages-inline`: Pre-flight inline cheap stages execution before heavy dispatch; mint stage receipts.
- `host-completion-and-install`: Workspace-scoped `install` skip; host-completion landing gate verification.
- `acceptance-and-flags`: False-reuse safety matrix; verify hours avoided; remove `tool_receipts` beta flag.

---

## 4. Crystal-Clear Epic Landing Criteria

### Epic E3 Landing Criteria
1. **Deterministic Signature Extraction:**
   - Running a test command with deliberate test and lint failures produces a non-empty `failures` array in `sase tool show <id> --json`.
   - Signatures contain zero workspace paths (`sase_\d+/` is completely stripped) and are invariant to shifting line numbers in test bodies.
2. **Accurate Three-Tier Classification:**
   - Runs matching `master` baseline classify `sase-j0` failures as `KNOWN` with attribution to bead `sase-j0`.
   - New assertions or syntax errors are explicitly classified as `NEW`.
   - Timeouts or SIGKILLs are classified as `INFRA_FAILURE`, not `NEW` test failures.
3. **CLI & Continuation Surfaces:**
   - `sase tool failures` displays active host failure groups, affected agents, and first-seen timestamps.
   - `sase tool rerun <id>` launches attempt $N+1$ linked to the original run.
   - Failing monitor prompts generated by `followup_prompt.py` embed structured failure triage without manual `--next` prose.
4. **Clean Exit:**
   - `tool_failure_triage` beta flag is deleted.
   - `sase-core-revision.txt` is ratcheted past the landed Rust contracts.
   - `just check` passes with zero warnings.

### Epic E4 Landing Criteria
1. **Receipt Minting and Instant Reuse:**
   - Running `sase tool run check` on a clean passing tree mints a `tree` receipt in `runs.sqlite`.
   - `sase tool receipt check` exits with code 0.
   - A subsequent `sase tool run check` completes in **under 1.0 second**, prints `Reusing pass receipt <id>`, and spawns no child subprocesses.
2. **Invalidation and Force Bypass:**
   - Touching any tracked source file causes `sase tool run check` to execute a fresh run.
   - Running `sase tool run check -R` on an unchanged tree forces execution and mints an updated receipt.
3. **Deterministic Failure Refusal:**
   - Re-running an unchanged tree after a deterministic failure exits code 2 with `Nothing has changed since run <id> failed. Use -R to force.`
   - Infra aborts are exempted from refusal.
4. **Cheap-Stages-First Inline Execution:**
   - Running `sase tool run -H check` on a tree with a lint violation fails inline in the foreground within 15 seconds without detaching a background monitor/proc.
5. **Host-Owned Landing Gate:**
   - Host landing scripts verify receipts non-interactively via `sase tool receipt check`.
6. **Clean Exit:**
   - `tool_receipts` beta flag is deleted.
   - `sase-core-revision.txt` is ratcheted past the landed Rust contracts.
   - `just check` passes with zero warnings.

---

## 5. Artifact Snapshot & Next Steps

The complete research report has been committed to the research sidecar repo and indexed as a durable artifact snapshot:
- **Report Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/sase/repos/research/202609/sase_tool_e3_e4_readiness_and_landing_criteria__gem.md`
- **Artifact Label:** `research:202609/sase_tool_e3_e4_readiness_and_landing_criteria__gem.md`
- **Ref:** `file:explicit:51fa4d1ff4e3cd9ba4bbc83b`
- **Declaration:** Completed and accepted via `sase final submit`.

**Recommended Immediate Next Move:**  
Once E2 (`sase-17p.6`) closes, authorize the E3 epic plan (`tool_e3_failure_triage.md`) using `/sase_plan` to begin implementing failure triage and attempt chains.
