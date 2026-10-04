# Chat History - ace-run (research.e.gem)

- **TIMESTAMP:** 2026-09-25 20:45:30 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.e.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_203638.md`

## Prompt

%id(gem, clan=research.e)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.e.cdx`, `research.e.cld`, `research.e.grk`, `research.e.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to start
grouping sets of scheduled routines in different nav sections. For example, I was
thinking that all builtin routines should be grouped together (I'm not sure how to group
the other routines).

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

# Research Synthesis: Nav Section Partitioning for Scheduled Routines in the Services Tab

- **Researcher:** `research.e.gem` (Gemini 3.8 Flash)
- **Swarm Peer Scope:** Independent research conducted without inspecting or consulting peer reports (`__cdx.md`, `__cld.md`, `__grk.md`, `__mus.md`).
- **Research Report Location:** [`sase/repos/research/202609/scheduled_routines_nav_sections__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/research/202609/scheduled_routines_nav_sections__gem.md)
- **Durable Snapshot Ref:** `file:explicit:aa6923bf664a593226cf88d7` (Label: `research:202609/scheduled_routines_nav_sections__gem.md`)

---

## 1. Executive Summary & Direct Critique

### Is splitting routines into multiple nav sections a good idea?
**No, implementing this as separate Nav Sections (stacked bordered panels) is not recommended.** However, the underlying motivation—**logically organizing routines as they grow**—is sound.

There are two major architectural and cognitive flaws in the initial plan:

1. **The Terminal Geometry Crisis (Screen Real Estate Overhead)**:
   In canonical SASE architecture ([`glossary:nav-section`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/memory/glossary/nav-section.md)), a **nav section** is a complete bordered panel in the left navigation column (like `#service-procs-panel` and `#scheduled-routines-panel` on the Services tab, or `@tribe` panels on the Agents tab).
   - In Textual, each bordered panel consumes **2 border lines**, **1 title line**, and an inter-panel separator.
   - For $N$ stacked panels, fixed chrome overhead is $3N - 1$ rows. Stacking 3 panels consumes **8–9 lines** of fixed overhead; 4 panels consumes **11–12 lines**.
   - In standard 24- to 35-line terminal windows, content space completely collapses. Each routine panel is reduced to a 2- to 3-line peephole with independent vertical scrollbars ("scrollbar soup"). Because routines expand vertically to show subordinate jobs (chops), expanding even one routine like `hooks` (8 chops) or `housekeeping` (9 chops) forces aggressive scrolling.

2. **The "Builtin vs. Other" Taxonomy Is Asymmetric and Semantically Empty**:
   - **Extreme Asymmetry:** Currently, SASE ships with **7 builtin routines** (`hooks`, `waits`, `checks`, `usage`, `external_mirror`, `comments`, `housekeeping`) spanning over 30 jobs. In contrast, typical installations have only **0, 1, or 2 custom/plugin routines** (such as `telegram`). Grouping by "builtin" vs. "other" leaves one massive, overflowing box next to a nearly empty panel.
   - **The Empty-Panel Anti-Pattern:** For projects without custom routines, an "Other" panel either wastes 4 lines displaying `"No routines configured"` or dynamically vanishes, causing jarring layout shifts.
   - **Operational Intent vs. Packaging Origin:** Operators monitoring background automation do not ask *"Is my python-wheel routine running?"*; they ask *"Are PR review hooks progressing?"*, *"Are notifications delivering?"*, or *"Is disk pressure triggering?"*. Lumping hourly database compaction with 5-second git lifecycle hooks simply because both are "builtin" provides zero domain insight.

---

## 2. Recommended Alternative & Adjustments to Requirements

### Adjustment 1: Functional Domain Grouping (Taxonomy)
Classify routines by **operational purpose** rather than origin:
- **`Lifecycle & Workflows`** (`hooks`, `waits`): High-cadence Patch/CL progression, mentor execution, hook checks (5s–10s intervals).
- **`Integrations & Connectors`** (`telegram`, `external_mirror`, `comments`): External boundary sync, notification delivery, issue mirroring (5s–15m intervals).
- **`System & Maintenance`** (`housekeeping`, `checks`, `usage`): Quota tracking, disk/tmp reaping, artifact backfill, periodic triage (1m–1h intervals).

### Adjustment 2: In-List Grouping Sections (Presentation)
Instead of creating multiple bordered *Nav Section panels*, implement **In-List Category Dividers or Collapsible Group Banners** inside the existing `#scheduled-routines-panel`:
- **Zero Border Overhead:** Conserves 100% of vertical height. Only a single stylized divider line (e.g. `── LIFECYCLE ──`) separates groups.
- **Frictionless `j`/`k` Traversal:** Preserves continuous cursor movement without border-crossing Textual focus jumps or class swapping.
- **Precedent:** Follows established SASE patterns, such as the `── oneshots ──` divider in `BgCmdList` and `Tasks`/`Phases` banners in Beads.

---

## 3. Implementation Comparison

| Dimension | Option A: In-List Dividers (Recommended) | Option B: Multi-Panel Nav Sections |
| :--- | :--- | :--- |
| **Space Overhead (24-line TUI)** | **0 extra border rows** (works on any screen) | **8–11 rows lost to chrome** (unusable) |
| **Expansion Flexibility** | Chops expand naturally in fluid scrolling list | Chops immediately clip and force panel scroll |
| **Navigation Flow** | Smooth, continuous `j`/`k` movement | Requires Tab/Shift-Tab across panels; border focus flicker |
| **Implementation Scope** | Row formatting in `_bgcmd_list_rows.py` and sorting in `_loader_items.py` | Full rewrite of `_panels.py`, `_render_panels.py`, `_app_layout.py`, and `allocate_panel_heights()` |
| **Rust / Schema Impact** | Purely optional (can be visual or schema-backed) | Required (dynamic panel definitions and schema updates) |

---

## 4. Recommended Action Plan

1. **Phase 1 (In-List Dividers):**
   - Define domain mappings (`DEFAULT_ROUTINE_CATEGORIES`) in `src/sase/axe/chop_inventory.py`.
   - Update `_append_lumberjack_items()` in `src/sase/ace/tui/actions/axe_display/_loader_items.py` to sort routines by category and flag group boundaries.
   - Update `format_lumberjack_option()` in `src/sase/ace/tui/widgets/_bgcmd_list_rows.py` to render section divider headers above the first routine of each category (similar to `_DIVIDER_LABEL = "── oneshots ──"`).
2. **Phase 2 (Config Extensibility):**
   - Add an optional `category: string` field to `axe.routines` in `src/sase/config/sase.schema.json` and `LumberjackConfig` in `src/sase/axe/_config_types.py`, allowing plugins (like `sase-telegram`) and user configs to specify custom categories.
3. **Phase 3 (Collapsible Group Nodes - Optional):**
   - If operators want to hide entire domains, category headers can be registered as foldable tree nodes in `_axe_fold_manager` (`category:lifecycle`), toggled with `Space`/`Enter`.

---

## 5. Artifact & Turn Summary

- **Research Report:** Created at [`sase/repos/research/202609/scheduled_routines_nav_sections__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/research/202609/scheduled_routines_nav_sections__gem.md).
- **Artifact Registered:**
  - `id`: `explicit:aa6923bf664a593226cf88d7`
  - `label`: `research:202609/scheduled_routines_nav_sections__gem.md`
  - `stored path`: `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260925203643/scheduled_routines_nav_sections__gem-3a2a2c9bc04f.md`
- **Host Finalizer Declaration:** Completed and accepted via `sase final submit -`.
