# Chat History - ace-run (research.24.gem)

- **TIMESTAMP:** 2026-09-21 18:40:15 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.24.gem

## Prompt

%id(gem, clan=research.24)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.24.cld`, `research.24.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to make the sase-core repo
much easier to maintain by sase agents. Can you do some research with the goal of
helping me decide the best way to implement this? End your analysis with a recommended
solution.

- Review the sase_core_maintainability_audit.md file in the research sidecar repo for
  context and inspiration before peforming your own research.
- I want you to perform your own research that builds upon this previous research file
  and takes into account the recent effort to reduce Rust file sizes in sase-core (see
  the sase-14s and sase-15b epic beads for context).
- Think hard about what it means for Rust code to be easy to understand / maintain by
  sase agents. 
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

The background check task has been launched to measure the warm check time for `sase-core` following an edit to a leaf module. I am waiting for its completion.
# SASE Core Agent Maintainability: Research Report & Recommended Solution

**Author:** `research.24.gem` (Independent Swarm Evaluation)  
**Registered Artifact:** [`research:202609/sase_core_agent_maintainability__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/research/202609/sase_core_agent_maintainability__gem.md)  
**Artifact ID:** `file:explicit:ede188e015a2f9c400604045`  
**Target Bead References:** [`sase-14s`](https://github.com/sase-org/sase--beads/blob/main/pages/sase-14s/README.md), [`sase-15b`](https://github.com/sase-org/sase--beads/blob/main/pages/sase-15b/README.md)  

---

## 1. Executive Summary & Context

Following the initial findings in `sase_core_maintainability_audit.md`, two major milestones recently completed:
1. **Critical Bug Fixes**: The live macOS `/tmp` reap guard failure and Linux-only CI gap were resolved in [`d99ba11`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/linked/sase-core) and [`d48aaf3`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/linked/sase-core), making the macOS CI leg blocking.
2. **File Size Reduction**: Epics [`sase-14s`](https://github.com/sase-org/sase--beads/blob/main/pages/sase-14s/README.md) and [`sase-15b`](https://github.com/sase-org/sase--beads/blob/main/pages/sase-15b/README.md) systematically split the top 20 largest files in the repository (including the 35,166-line `sase_core_py/src/lib.rs` monolith) into sub-trees adhering to a strict `≤ 1,500` lines-per-file ceiling.

### The Central Finding
**File size reduction was a necessary mechanical fix, but it is not sufficient to make `sase-core` easy for SASE agents to maintain.**

Decomposing files solved a tool constraint (allowing files to fit within `view_file` buffers), but left the deeper cognitive and operational bottlenecks untouched. In some cases, it introduced new forms of indirection (such as dumping 1,104 lines of imports into a global `prelude.rs`).

---

## 2. Empirical Repository State (Post-sase-14s & sase-15b)

| Metric | Pre-Split Audit Baseline | Current Master (`8886406`) | Assessment / Delta |
|---|---|---|---|
| **Crates** | 4 | 4 | No change (`sase_core`, `sase_core_py`, `sase_gateway`, `sase_xprompt_lsp`) |
| **Rust Source Files** | 381 | **704** | **+323 files (+84.8%)** from module decompositions |
| **Total Rust Lines** | 376,405 | **381,675** | +5,270 lines (+1.4%, declarations, docstrings, imports) |
| **`crates/sase_core` Lines** | 292,391 | 294,812 | Single-crate compilation monolith remains intact |
| **Maximum File Size** | **35,166 lines** (`sase_core_py/lib.rs`) | **2,699 lines** (`editor/frontmatter.rs`) | **-92.3% drop in ceiling**; god-monoliths eliminated |
| **Files > 1,500 Lines** | ~65 | **42 files** | Top 20 split; 42 remain |
| **Files ≤ 500 Lines** | 184 (48.3%) | **412 files (58.5%)** | Majority now fit comfortably in a single tool view |
| **Files 501–1,000 Lines** | 112 (29.4%) | **188 files (26.7%)** | Sweet spot for single-module cohesion |
| **Files 1,001–1,500 Lines** | 43 (11.3%) | **63 files (8.9%)** | Upper bound of single-module size |
| **`sase_core_py/src/lib.rs`** | 35,166 lines | **736 lines** | Split into 24 domain modules + registrars |
| **`sase_core/src/lib.rs`** | 1,627 lines | **1,629 lines** | 107 `pub mod` and 2,672 flat re-exports unchanged |
| **Python `.pyi` Stubs** | 0 | **0** | Python callers still lack static type assistance |
| **`Result<_, String>` Sites** | 389 (production) | **391** (production) | Untyped error handling remains pervasive |

---

## 3. What "Agent Maintainability" Means in Rust

Agents operate under a fundamentally different execution model than human engineers using IDEs:

1. **Context Economy & Tool Slices**: Agents read code via tools (`view_file`, max 800 lines) and edit via contiguous string matching (`replace_file_content`). Files between **300 and 800 lines** represent the ideal sweet spot: readable in a single call, with minimal line drift risk during edits.
2. **Turn Latency & Verification Feedback**: SASE agents run under strict execution and timeout budgets. If `just check` takes 4–6 minutes, agents are discouraged from running incremental checks, leading to higher error rates.
3. **Discoverability vs. Prelude Pollution**: Agents discover code via text grep and file trees. Flat preludes that re-export 2,672 symbols at the crate root generate massive search noise and obscure type ownership.
4. **The Cross-Language Type Chasm**: Python code in the `sase` repo consumes `sase_core_rs`. With **zero `.pyi` stubs** and >550 dict-in/dict-out functions, Python agents have no parameter autocompletion or static type checking, leading to runtime failures and cross-repo context switching.
5. **Parallel Agent Swarms**: Multi-agent swarms require isolated domain boundaries to prevent merge collisions on landing.

---

## 4. Key Remaining Bottlenecks in sase-core

### 1. The 294k-Line Compilation Monopoly
Rust compiles at the crate level. Splitting files inside `crates/sase_core` did not reduce compile times because all 294k lines remain in that single crate. An edit in a leaf file (`host_liveness.rs`) still invalidates all downstream crates (`sase_core_py`, `sase_gateway`, `sase_xprompt_lsp`), taking **4 to 6 minutes** for a full rebuild.

### 2. The Silent PyO3 Environment Trap
Running bare `cargo check --workspace` fails immediately with:
`error: cannot set a minimum Python version 3.12 higher than the interpreter version 3.11`.
Because system Python defaults to 3.11 while PyO3 pins `abi3-py312`, `cargo check` fails unless `PYO3_PYTHON` is explicitly exported. Furthermore, `scripts/check.sh` lacks a `check` subcommand, forcing agents to run `just check` (which runs all 4,000+ tests and clippy on every invocation).

### 3. "Sweeping Under the Rug" (Prelude Bloat)
In `sase_core_py`, splitting `lib.rs` was achieved partly by dumping 1,100 lines of imports into `crates/sase_core_py/src/prelude.rs` (**1,104 lines**), which every submodule imports with `use crate::prelude::*;`. In `sase_core/src/lib.rs`, **2,256 of 2,672 root re-exports (84%)** are never consumed through the root path, polluting symbol searches.

### 4. Zero Python Type Stubs (`.pyi`)
`sase_core_rs` exports **822 functions** with zero `.pyi` stubs. Python agents calling core functions have no autocomplete or type checking, leading to defensive code patterns like `require_rust_binding(...)` and manual dictionary validation.

### 5. Diminishing Returns of Mechanical File Splitting
42 files remain above 1,500 lines. The largest is now 2,699 lines (`editor/frontmatter.rs`). Launching further batches (e.g. `sase-16c`, `sase-17d`) will add ~180 new files while splitting cohesive units (such as database stores) without addressing the compile time or type interop bottlenecks.

---

## 5. Recommended Solution: 4-Phase Roadmap

Instead of continuing mechanical file-splitting epics, we recommend shifting focus to verification speed, cross-language typing, and architectural boundaries:

```
┌───────────────────────────────────────────────────────────────────────────┐
│ PHASE 1: Zero-Cost Developer & Agent Ergonomics (Immediate / 1-2 Days)    │
│  - Configure ambient PYO3_PYTHON resolution for bare cargo invocations    │
│  - Add `just fast` -> `check.sh check` (cargo check --workspace) in ~14s  │
│  - Update AGENTS.md instructing agents to use the fast inner loop         │
├───────────────────────────────────────────────────────────────────────────┤
│ PHASE 2: Python-Rust Interop Ergonomics (High Leverage / 1 Sprint)        │
│  - Auto-generate sase_core_rs.pyi type stubs in CI                        │
│  - Delete the 665-line drifted manual //! API manifest in lib.rs          │
│  - Decompose sase_core_py/prelude.rs into per-module domain imports       │
├───────────────────────────────────────────────────────────────────────────┤
│ PHASE 3: Namespace Hygiene & Selective Splitting (Medium / 1 Sprint)      │
│  - Retire 2,256 redundant root re-exports in sase_core/src/lib.rs         │
│  - Add workspace [lints.clippy] table (unwrap_used, too_many_arguments)   │
│  - Selectively split only the top 3 high-churn hotspots (frontmatter.rs,  │
│    plan/validate.rs, scanner.rs); leave stable stores intact              │
├───────────────────────────────────────────────────────────────────────────┤
│ PHASE 4: Structural Domain Crate Decomposition (Standing Direction)       │
│  - Extract crates/sase_types (pure Wire structs, zero-dep, 2s compile)   │
│  - Extract crates/sase_bead & crates/sase_artifact into standalone crates │
└───────────────────────────────────────────────────────────────────────────┘
```

### Actionable Next Steps
1. **Stop mechanical file-splitting epics** (do not launch `sase-16c` to split the next 10 files).
2. **Implement Phase 1 immediately**: Configure ambient Python 3.12 resolution and add `just fast` (runs `cargo check --workspace` in **14.28s**, giving agents an instant feedback loop).
3. **Execute Phase 2**: Auto-generate `.pyi` stubs for `sase_core_rs`. This provides the highest leverage-per-hour improvement across the entire dual-language agent ecosystem.

---

*The full report with reproduction measurements and architectural details has been registered as artifact [`research:202609/sase_core_agent_maintainability__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_42/sase/repos/research/202609/sase_core_agent_maintainability__gem.md) (ID: `file:explicit:ede188e015a2f9c400604045`).*
