# Chat History - ace-run (research.08.gem)

- **TIMESTAMP:** 2026-10-04 08:45:41 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.08.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261004_083003.md`

## Prompt

%id(gem, clan=research.08)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.08.cdx`, `research.08.cld`, `research.08.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about starting to run the toobig_split job for other projects besides sase.

- This includes a few Rust, JavaScript, and Swift projects.
- These languages are not necessarily suited for the 700 line limit trigger used for or
  the 500 line limit recommendations given for Python files by the toobig_split job
  currently.
- I'm not sure what line limit trigger/recommendations I should use for these other
  languages.

Can you do some research with the goal of helping me decide? Also, critique this plan in
general. Is this a good idea? Would you take a different approach? Make any adjustments
to the requirements that you think are justified but clearly call these out. End your
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

# Multi-Language `toobig_split`: Architecture Critique, Cross-Language Line-Count Thresholds, and Operational Strategy

**Researcher:** `gem` (Independent Research Swarm)  
**Report File:** [`sase/repos/research/202610/toobig_split_multilang_thresholds_and_strategy__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/toobig_split_multilang_thresholds_and_strategy__gem.md)  
**Artifact ID:** `explicit:4e40c84247ae5df4ab002072`  
**Artifact Label:** `research:202610/toobig_split_multilang_thresholds_and_strategy__gem.md`

---

## 1. Executive Summary & Core Verdict

The plan to generalize `toobig_split` to Rust, JavaScript/TypeScript, and Swift is a valuable initiative for maintaining codebase readability, but **directly porting Python's 700-line trigger floor and 500-line split target as an autonomous background daemon will cause severe architectural degradation**.

* **In Rust**, 700 lines is standard module size. In [`sase-core`](file:///home/bryan/projects/github/sase-org/sase-core/), **28% of all files (261 out of 926 files)** exceed 700 lines (e.g. `scanner.rs` at 3,330 lines, `touch_index.rs` at 3,103 lines). An unadjusted 700-line trigger floor would trigger an uncontrolled swarm of hundreds of background agents across core modules.
* **In JavaScript/TypeScript**, modern UI components and plugin views (such as Obsidian plugin views) frequently require 500–800 lines to remain cohesive. Furthermore, bundled distribution artifacts (like `main.js` in [`bob-plugins`](file:///home/bryan/projects/github/bobs-org/bob-plugins/)) can reach 50,000+ lines and must be strictly excluded. Mechanical splits by LLMs also risk introducing runtime ESM circular dependencies (Temporal Dead Zone).
* **In Swift**, access control is lexical (`private` and `fileprivate` are file-scoped). Splitting a file across multiple files breaks `fileprivate` boundaries, forcing internal implementation details to be exposed as `internal`. In addition, stored properties cannot be declared in extensions.

### High-Level Recommendation
1. **Calibrate line-count thresholds** to language verbosity and idioms (**1,500 / 1,000 for Rust**, **800 / 500 for JS/TS and Swift**).
2. **Switch from an autonomous background chopping daemon to an Advisory Triage Model**: Have the scheduled AXE job scan projects and emit **Task Beads** (`task_type: feature` / refactoring triage) rather than immediately dispatching code-modifying agent swarms.
3. **Use Language-Specific Split Macros** (`#split_file_rust`, `#split_file_ts`, `#split_file_swift`) tailored to the module system, test patterns, and verification harnesses of each language.

---

## 2. Recommended Quantitative Thresholds

| Language | Hard Limit (Exit 1) | Warning Threshold | Info / Trigger Floor | Split Recommendation (Target) | Accounting & Exclusions |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Python** *(Baseline)* | 1,000 | 850 | **700** | **500** | Exclude comments & docstrings |
| **Rust** *(Total LOC)* | 2,000 | 1,700 | **1,500** | **1,000** | Standard idiomatic inline tests |
| **Rust** *(Excl. Tests)* | 1,500 | 1,200 | **1,000** | **750** | When `#[cfg(test)]` is separated |
| **JavaScript / TypeScript** | 1,200 | 950 | **800** | **500** | Exclude `dist/`, `build/`, `*.bundle.js`, `main.js` |
| **Swift** | 1,200 | 900 | **800** | **500** | Decompose via `Type+Domain.swift` extensions |

---

## 3. Linguistic Deep-Dive: Why Python's 700/500 Fails for Other Languages

### 3.1 Rust
1. **Syntactic Verbosity & Trait Boilerplate:**  
   Rust requires explicit type signatures, lifetime parameters, `where` clauses, `match` blocks, and extensive trait implementations (`Display`, `Debug`, `Serialize`, `Deserialize`, `From`, `Into`, `Default`). A single struct with idiomatic trait implementations can easily span 600 lines before any domain business logic is added.
2. **Inline Unit Tests (`#[cfg(test)] mod tests`):**  
   In idiomatic Rust, unit tests reside at the bottom of the source file. In `sase-core` and `bob-cli`, 30% to 50% of the lines in files over 1,000 LOC are unit tests. Splitting based on total LOC penalizes developers for writing thorough unit tests.
3. **Encapsulation Breakdown:**  
   Submodules in Rust cannot access private fields of sibling structs without declaring them `pub(crate)` or `pub(super)`. When LLMs are instructed to split a Rust file to satisfy a 500-line limit, their standard workaround for compiler errors is to make private fields `pub(crate)`. Doing this repeatedly across a repository destroys architectural encapsulation.
4. **Prior Art in SASE Config:**  
   In `~/.config/sase/sase.yml`, the user's existing `#split_epic` macro explicitly defines `lang: Rust, max_line_count: 1500`. Setting the trigger floor to 1,500 lines perfectly aligns with this existing intuition:
   * Files > 700 lines in `sase-core`: 261 (28.2%) — *too noisy, high false-positive rate*.
   * Files > 1,500 lines in `sase-core`: 59 (6.4%) — *high signal, genuine monoliths ripe for refactoring*.

### 3.2 JavaScript & TypeScript
1. **UI Components & Stateful Views:**  
   In React, Svelte, or Obsidian view plugins, a component encapsulating state, hooks, event handlers, and JSX markup naturally reaches 500–700 lines. Arbitrarily splitting it forces artificial prop drilling, extra context providers, or unnatural state abstractions.
2. **ESM Circular Dependency (Temporal Dead Zone):**  
   Splitting JS/TS files frequently introduces circular dependencies. While `tsc` often compiles circular imports without error, runtime ESM environments and bundlers (Vite/Rollup) will crash with `TypeError: Cannot read properties of undefined` due to uninitialized module exports.
3. **Bundled Distribution Traps:**  
   In repositories like `bob-plugins`, plugins frequently commit built output files (`main.js`) that exceed 10,000 to 50,000 lines. The scanning job must enforce strict exclusion globs (`dist/**`, `build/**`, `*.bundle.js`, `**/main.js`).

### 3.3 Swift
1. **Idiomatic Extension Architecture:**  
   In Swift, the standard way to split large types is across extension files (`User+Networking.swift`, `View+Subviews.swift`). Splitting must follow this pattern rather than arbitrary module subdivision.
2. **Access Control (`fileprivate` vs `internal`):**  
   `fileprivate` is strictly scoped to the file. Splitting a file forces previously file-private members to become `internal`, exposing implementation details to the entire build target.
3. **Stored Property Constraints:**  
   Swift forbids stored properties inside extensions. All stored properties must stay in the main declaration.
4. **Xcode PBX Project File Hazard:**  
   In Xcode-based projects (`.xcodeproj/project.pbxproj`), simply creating `NewFile.swift` on disk does not include it in the build target; the PBX file must be updated. For SwiftPM projects (`Package.swift`), directory discovery is automatic.

---

## 4. Critique of the Plan in General

### Is Running `toobig_split` Across Other Projects a Good Idea?

* **The Core Problem with Autonomous Periodic Daemon Runs:**  
  Running a background daemon every 60 minutes that autonomously refactors files across multiple projects creates substantial developer friction:
  - **Git Churn and Race Conditions:** Autonomous agents refactoring files while human developers (or other agents) are working on feature branches will cause painful merge conflicts.
  - **Single Responsibility Violation:** Refactoring should be intentional and driven by cohesion, not arbitrary line counts.
  - **Compiler Cost:** Running sequential clans that execute `cargo check` / `cargo test` in the background places a heavy CPU and cache burden on the machine.

### What Approach Should Be Taken Instead?

1. **Shift to Advisory Triage (Task Beads):**  
   Rather than immediately launching code-editing agents, the AXE routine should audit repositories on a daily schedule (or every 24h) and file **Task Beads** (`task_type: feature` / refactoring triage) when files cross the warning threshold.
2. **Human-in-the-Loop Execution:**  
   The developer reviews the bead in the SASE TUI Beads tab and triggers the split on-demand via a macro when the workspace is idle.
3. **Separate Test Code from Source Code:**  
   In Rust, the scanner should either exclude `#[cfg(test)]` modules or instruct the agent to move unit tests into a sibling `tests.rs` or `foo_test.rs` file before modifying production structures.

---

## 5. Recommended Solution & Action Plan

### Step 1: Update AXE Routine Configuration (`sase_athena.yml` / `sase.yml`)
Configure per-project language targets and thresholds in AXE:

```yaml
axe:
  routines:
    maintenance:
      jobs:
        toobig_audit:
          script: bugyi_chop_toobig_audit
          description: "Audit file line lengths across configured projects and emit triage beads"
          run_every: 24h
          for_each:
            source: projects
            names: [sase, sase-core, bob-cli, bob-plugins]
          targets:
            sase:
              lang: python
              trees: [src, tests]
              limits: [1000, 850, 700]
              target_split: 500
            sase-core:
              lang: rust
              trees: [crates]
              limits: [2000, 1700, 1500]
              target_split: 1000
              exclude_patterns: ["target/**", "**/bindgen.rs"]
            bob-cli:
              lang: rust
              trees: [src, tests]
              limits: [2000, 1700, 1500]
              target_split: 1000
            bob-plugins:
              lang: typescript
              trees: [plugins]
              limits: [1200, 950, 800]
              target_split: 500
              exclude_patterns: ["**/main.js", "**/dist/**", "**/node_modules/**"]
```

### Step 2: Introduce Language-Specific Split Macros
Replace the Python-specific `split_file.md` with:
- **`#split_file_rust`**: Focuses on `mod.rs` vs `foo.rs` structure, `pub(crate)` encapsulation hygiene, extracting `#[cfg(test)] mod tests` to a sibling test file, and verifying with `cargo check --all-targets` and `cargo test --lib`.
- **`#split_file_swift`**: Focuses on `Type+Domain.swift` extensions, preserving `fileprivate`, respecting the prohibition on stored properties in extensions, and checking Xcode target membership.
- **`#split_file_ts`**: Focuses on ESM cycle prevention, barrel file re-exports (`index.ts`), and verification via `tsc --noEmit` and `npm test`.

### Step 3: Phased Rollout
1. **Telemetry & Audit Only:** Run the audit in reporting mode across `sase-core`, `bob-cli`, and `bob-plugins` without dispatching agents.
2. **Advisory Triage Beads:** Enable AXE creation of triage task beads for files exceeding warning thresholds.
3. **Interactive Splitting:** Invoke language-specific split macros on-demand for targeted files during dedicated maintenance windows.

---

## 6. Durable Artifact Details

The complete, unabridged research document has been written to the research sidecar repository and registered as a durable artifact snapshot:

* **Local Workspace File:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/toobig_split_multilang_thresholds_and_strategy__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/toobig_split_multilang_thresholds_and_strategy__gem.md)
* **Registration Command:**
  ```bash
  sase artifact create \
    -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/toobig_split_multilang_thresholds_and_strategy__gem.md" \
    -l "research:202610/toobig_split_multilang_thresholds_and_strategy__gem.md"
  ```
* **Artifact Ref:** `file:explicit:4e40c84247ae5df4ab002072`

The finalizer declaration for the `commit` payload on repository `sdd:research` (`repo-8caa19a02d02`) has been successfully submitted and accepted:

* **Repository:** `sdd:research` (`repo-8caa19a02d02`)
* **Target Path:** [`202610/toobig_split_multilang_thresholds_and_strategy__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/toobig_split_multilang_thresholds_and_strategy__gem.md)
* **Commit Message:** `docs(research): analyze multi-language toobig_split thresholds and strategy`
* **Status:** Accepted declaration; host finalizer will execute commit upon completion of this turn.
