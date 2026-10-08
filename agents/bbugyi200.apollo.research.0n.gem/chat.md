# Chat History - ace-run (research.0n.gem)

- **TIMESTAMP:** 2026-10-08 14:09:24 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0n.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_135159.md`

## Prompt

%id(gem, clan=research.0n)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.0n.cdx`, `research.0n.cld`, `research.0n.grk`, `research.0n.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would like to make the sase-listen repo a first-class sase plugin.

- To support this change, we should start allowing sase plugins to define sub-commands
  somehow.
- The sase-listen plugin should use this new functionality to define the `sase listen`
  command.
- This command should work exactly like the `sase-listen` command, but should support
  sase's CLI completion (make sure that completion is updated automatically when a
  plugin like this is installed).
- We should also start displaying this plugin on the "Updates" tab of the "SASE Admin
  Center" panel so users can manage its installation the same way they do for other sase
  plugins. I have already added the `sase--plugin` GitHub label on sase-listen's GitHub
  repo to support this.

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

# Research Report: First-Class `sase-listen` Plugin & Plugin Subcommand Architecture

**Author:** Researcher `gem` (Swarm Evaluation)  
**Report Location:** [`sase_listen_plugin_and_subcommand_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/sase_listen_plugin_and_subcommand_architecture__gem.md)  
**Durable Artifact Snapshot:** `research:202610/sase_listen_plugin_and_subcommand_architecture__gem.md` (`file:explicit:438d1e52bb142b29c73be24a`)

---

## 1. Executive Summary & Verdict

Making [`sase-listen`](https://github.com/sase-org/sase-listen) a first-class plugin providing `sase listen` is a **sound and high-value architectural move**, because listening to markdown research deliverables on commutes directly aligns with SASE's heavy agent workflows.

However, the implementation requires strict attention to **CLI latency preservation**, **two subtle gaps in SASE's completion update lifecycle**, and **CLI convention consistency**.

---

## 2. Key Findings & Critique of the Plan

### 2.1 Is This a Good Idea?
- **Strong Alignment:** Unifying `sase-listen` under `sase listen` creates an intuitive interface for consuming research reports (e.g. `sase listen render research:202610/report.md`). Managing it via `sase plugin install listen` and `sase update` avoids fragmentation across distinct tools.
- **Dependency Weight & Startup Latency Hazard:** `sase-listen` brings in heavy dependencies (`google-genai`, `numpy`, `imageio-ffmpeg`, `pillow`, `curl_cffi`, `lxml`, `pdfminer.six`). SASE’s core CLI relies on sub-10ms response times. **Zero eager imports** may occur during normal `sase` commands or tab-completions; discovery and execution must be strictly lazy.
- **Command Namespace Protection:** Built-in commands (`bead`, `patch`, `plan`, `tool`, `agent`, etc.) must be reserved. Any third-party plugin attempting to shadow core commands or colliding with an existing plugin must fail closed.

### 2.2 Mechanism Evaluation: How Plugins Should Define Subcommands
We evaluated three candidate architectures:
1. **Python Entry Points (`sase_commands`) [Recommended]:** Standard packaging entry point group `[project.entry-points."sase_commands"]`. Zero core overhead until invoked; native `argparse` integration; full automatic shell completion tree traversal via `build_spec`.
2. **Pluggy Hooks:** Over-engineered for 1-to-1 CLI subcommand routing. Requires importing hook classes and instantiating plugin managers even for simple lookups.
3. **Subprocess Delegation (`git-foo` style):** Simple process isolation, but completely breaks SASE’s in-process `build_spec` shell completion introspection and unified Rich styling/error handling.

### 2.3 Shell Completion: Two Critical Gaps Discovered
1. **Missing Post-Mutation Hook:** `sase plugin install`, `update`, and `uninstall` currently do *not* call `maybe_refresh_installed_completions()`, unlike `sase update`.
2. **Grammar Cache Invalidation Blindness:** SASE's shell completion runtime cache (`runtime_cache_identity.py`) hardcodes `_DISTRIBUTIONS = ("sase", "sase-core-rs")` and hashes only SASE's own package files. Installing or uninstalling a plugin does not change the cache digest key, causing existing shells to silently serve stale completion scripts. Both must be fixed.

### 2.4 Admin Center Updates Tab Status
- The user added the topic `sase--plugin` to `sase-org/sase-listen` (verified via `gh api repos/sase-org/sase-listen --jq .topics`).
- Because SASE queries GitHub repository topics (`topic:sase--plugin`), `sase-listen` **already appears** as an official built-in plugin in `sase plugin list` and the Admin Center Updates tab once refreshed (`sase plugin list --refresh`).
- What needs updating is registering `sase_commands` in `installed.py` so the detail view shows `Contributed: sase_commands (listen)`.

---

## 3. Recommended Adjustments to the Requirements

| # | Original Requirement | Recommended Adjustment | Justification |
| :- | :--- | :--- | :--- |
| **1** | "Define sub-commands somehow" | Use PEP 517/621 entry-point group `sase_commands` with lazy registrar functions | Standard, robust, avoids Pluggy overhead, preserves sub-10ms CLI latency. |
| **2** | "Work exactly like `sase-listen`" | Retain standalone `[project.scripts] sase-listen` alongside `sase listen` | Allows `sase-listen` to remain usable standalone in scripts, CI, and external workflows without requiring SASE. |
| **3** | `sase-listen` command structure | Provide `list` command (aliasing `ls`) and bare list delegation | Conforms to SASE CLI standard ([`cli_rules.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/cli_rules.md)) where command groups must support `list` and bare execution delegates to `list`. |
| **4** | "Support CLI completion" | Fix cache invalidation in `runtime_cache_identity.py` and add completion hook in `cli_install.py` | Without these core fixes, installing a plugin will fail to update shell completions automatically. |
| **5** | SASE Artifact integration (Value-Add) | Allow `sase listen render` to accept SASE artifact references (`research:...`, `plan:...`) | Elevates `sase-listen` from an external tool to a true first-class SASE citizen. |

---

## 4. Implementation Blueprint

### 4.1 In `sase` Core
1. **Entry Point Group:** Define `sase_commands` in `docs/plugins.md`.
2. **Lazy Parser Detection (`src/sase/main/parser_registry.py`):**
   - Check `_COMMAND_REGISTRARS` first (built-in commands incur 0.00ms overhead).
   - Only if `candidate not in _COMMAND_REGISTRARS`, check `importlib.metadata.entry_points(group="sase_commands")`.
   - When matched, narrow `only=candidate` so only that plugin's registrar is loaded.
3. **Execution Dispatch (`src/sase/main/entry.py`):**
   - Before the "Unknown command" fallback exit, execute `handler(args)` if `getattr(args, "func", None)` or `getattr(args, "_command_handler", None)` is callable.
4. **Completion Invalidation & Refresh:**
   - Update `runtime_cache_identity.py` to include distributions providing `sase_commands` in `_distribution_records()`.
   - Call `maybe_refresh_installed_completions()` after package mutations in `src/sase/plugins/cli_install.py`, `cli_uninstall.py`, and `cli_update.py`.
5. **Catalog Recognition:**
   - Add `sase_commands` to the recognized contributed entry-point groups in `src/sase/plugins/installed.py`.

### 4.2 In `sase-listen`
1. **`pyproject.toml`:**
   ```toml
   [project.scripts]
   sase-listen = "sase_listen.cli:main"

   [project.entry-points."sase_commands"]
   listen = "sase_listen.sase_plugin:register_listen_parser"
   ```
2. **`src/sase_listen/sase_plugin.py`:**
   - Expose `register_listen_parser(subparsers)` attaching the `listen` subparser with all 11 subcommands and rich help formatters.
   - Add `list` as an alias for `ls` to follow SASE CLI rules.
3. **Artifact Resolution (Enhancement):**
   - In `render <source>`, detect SASE artifact references (`research:`, `plan:`, `file:`) and resolve them via `sase artifact path <ref>`.

---

## 5. Artifact & Turn Record

- **Research Report:** [`sase/repos/research/202610/sase_listen_plugin_and_subcommand_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/sase_listen_plugin_and_subcommand_architecture__gem.md)
- **Registered Artifact:** `research:202610/sase_listen_plugin_and_subcommand_architecture__gem.md` (`explicit:438d1e52bb142b29c73be24a`)
- **Finalizer Declaration:** Submitted and accepted (`sase final submit -`).
