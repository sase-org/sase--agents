# Chat History - ace-run (research.49.gem)

- **TIMESTAMP:** 2026-10-11 09:15:53 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.49.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261011_085313.md`

## Prompt

%id(gem, clan=research.49)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.49.cdx`, `research.49.cld`, `research.49.grk`, `research.49.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
want to add support to the "Projects" tab of the "SASE Admin Center" panel for creating
new projects.

- New projects should be enabled by default.
- The user should be prompted to select what VCS they want their project to use.
- It should then prompt them to select from a menu that includes projects that the user
  is likely to add based on their VCS selection (e.g. the GitHub projects that are
  associated with their configured GitHub organizations but not yet associated with a
  sase proeject).
- The user should also have the option to create a new project from scratch, in which
  case we should use the appropriate VCS plugin to create a new repo (e.g. the
  sase-github plugin could implement this using the `gh` command to create the
  approprate repo, for example).
- If creating a new repo, make sure we prompt the user for all of the same options
  supported by the VCS provider (e.g. public/private, GitHub repo description, etc...).
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
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Findings: Adding Project Creation to the SASE Admin Center

**Report Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/admin_center_project_creation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/admin_center_project_creation__gem.md)  
**Registered Artifact Ref:** `research:202610/admin_center_project_creation__gem.md` (`file:explicit:b9db38cf2ea14f6d94c9ab79`)

---

## 1. High-Level Verdict & General Critique

Adding project creation directly to the **Projects** tab of the **SASE Admin Center** (`#` modal → `ProjectsPane`) is an **outstanding and overdue idea**. 

Currently, the Projects tab is strictly an inspection and maintenance interface (enable, disable, mark, delete, aliases, edit spec, init). Projects can only be created via implicit prompt triggers (e.g., mentioning `#gh(owner/repo)` in an agent prompt to trigger auto-cloning), manual directory creation under `~/.sase/projects/`, or low-level CLI commands. A first-class, interactive onboarding workflow establishes the Admin Center as the operational control hub for SASE.

However, the initial plan requires critical refinements:

1. **Conflating "Importing Existing Repos" with "Greenfield Provisioning":**
   - Selecting an existing repository from configured GitHub orgs (import/adoption) is fundamentally different from provisioning a brand-new repository on GitHub from scratch.
   - Forcing both into a single linear form leads to confusing UX. The wizard should clearly fork at Step 1 into two dedicated pathways: **Import Existing Repository** and **Create Greenfield Repository**.
2. **The "Prompt for ALL VCS Options" Anti-pattern:**
   - Attempting to replicate all 15+ options of `gh repo create` (custom team access, template repos, 100+ gitignore options, 60+ license choices, wiki/issues toggles) in a terminal Textual form violates SASE TUI performance rules (`tui_perf.md`) and produces an overwhelming, cluttered wall of inputs.
   - **Recommended Adjustment:** A clean 80/20 form capturing the core fields (Owner/Org, Name, Visibility, Description, README/gitignore toggles) with an escape hatch: `[Open Interactive gh in Terminal]` via Textual's `app.suspend()`.
3. **VCS Selection Step Friction:**
   - Prompting "Choose VCS: [GitHub] [Bare Git]" every time adds friction when `sase-github` is the user's primary or only configured provider. The wizard should intelligently default to GitHub while enabling quick tab switching.
4. **Local Repository Adoption Gap:**
   - The original plan overlooks importing existing local Git directories on disk (`~/projects/...`). Supporting local repository adoption is simple, offline-friendly, and covers a common developer workflow.
5. **Backend & CLI Parity:**
   - Domain logic must not live only inside Textual UI widgets. In accordance with SASE Rule 1.3 (Rust Core / backend boundary), the workflow engine belongs in the workspace provider hook system (`WorkspaceHookSpec`), exposed via CLI subcommands (`sase project add` and `sase project create`).

---

## 2. Recommended Adjustments to Requirements

| # | Proposed Requirement Adjustment | Motivation & Rationale |
|---|---------------------------------|------------------------|
| **1** | **Two-Pathway Onboarding** | Clear split between **Import Existing Remote Repo** and **Create Greenfield Repo**. |
| **2** | **Streamlined Greenfield Form (80/20 Rule)** | Keep the modal clean, responsive, and beautiful with core fields + terminal escape hatch for exotic options. |
| **3** | **Smart VCS Defaulting** | Auto-select GitHub if configured in `github_orgs`, without locking out Bare Git or Local Git. |
| **4** | **Local Directory Adoption** | Allow users to register existing local Git repositories directly by path. |
| **5** | **Async Resilient Loading & Filter** | Fetch GitHub org repositories off-thread with live substring filtering and clear auth/network diagnostics. |
| **6** | **Formal Hookspec Extension** | Extend `WorkspaceHookSpec` with `ws_create_remote_repo(...)` to keep SASE core decoupled from VCS plugins. |
| **7** | **CLI Parity (`sase project add/create`)** | Ensure full scriptability and testing parity outside the TUI. |

---

## 3. Recommended UX & Visual Design

### Entry Point
- In `ProjectsPane` (`src/sase/ace/tui/modals/projects_pane.py`), bind the unmapped key **`n`** (`create_project`) to open the wizard modal.
- Update the footer key hints line to prominently display `n new project`.

### The Wizard Modal: `NewProjectWizardModal`
A multi-step, 3-stage modal styled with SASE accent colors (`#FFAF5F` orange, `#00D7AF` green, `#87D7FF` cyan):

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ ✦ SASE Admin Center — Add / Create Project                             [Esc]│
├─────────────────────────────────────────────────────────────────────────────┤
│  [1. Source & VCS] ───▶ [2. Configure / Select] ───▶ [3. Provision & Setup] │
└─────────────────────────────────────────────────────────────────────────────┘
```

1. **Step 1: Source & Mode Chooser**
   - Options:
     - `(●) 1. Import Existing Remote Repository` (from GitHub orgs)
     - `(○) 2. Create Brand New Repository` (greenfield creation via `gh`)
     - `(○) 3. Adopt Local Directory` (register existing local Git repo)
   - VCS Provider toggle: `[ GitHub ]` | `[ Git (bare/local) ]`
2. **Step 2A: Remote Repository Browser (Import Flow)**
   - Organization tabs (`sase-org`, `bbugyi200`) showing available repo counts.
   - Live filter input (`/`) with instant debounce search.
   - Candidates table excluding repos already in SASE.
   - Detail pane showing repo description, visibility badge, clone target, and last pushed date.
3. **Step 2B: Greenfield Creation Form (Create Flow)**
   - Owner/Org selector dropdown.
   - Repository Name input with live slug validation (`gh_<owner>__<repo>`).
   - Visibility pill selector: `(●) Private` | `(○) Public` | `(○) Internal`.
   - Description input (optional).
   - Scaffolding toggles: `[✓] Add README.md`, `[✓] Add .gitignore [Python/Rust/...]`.
4. **Step 3: Provisioning & Progress Overlay**
   - Live checklist with animated progress:
     - `[✓] Creating remote repository on GitHub via gh...`
     - `[✓] Initializing remote repository with scaffolding...`
     - `[⟳] Cloning repository to ~/projects/github/org/repo/...`
     - `[ ] Writing SASE project specification file...`
     - `[ ] Configuring SDD sidecar repository...`
     - `[ ] Registering project in Admin Center...`
   - On completion, toast notification: `Project '<name>' added (enabled)`.
   - Highlights the newly added project row upon returning to `ProjectsPane`.

---

## 4. Technical Architecture & Phased Roadmap

### Core Architecture
- **Hookspec Extension (`src/sase/workspace_provider/_hookspec.py`):**
  Add `ws_create_remote_repo(workflow_type, options)` returning typed `VcsCreateRepoResult`.
- **Plugin Implementation (`sase-github`):**
  Implement non-blocking `gh repo create` and `git clone` using `non_interactive_gh_env()` with `stdin=subprocess.DEVNULL` to prevent terminal freezes.
- **CLI Commands (`src/sase/main/project_handler.py`):**
  Implement `sase project add <ref-or-path>` and `sase project create <name> [flags]`.
- **TUI Presentation (`src/sase/ace/tui/modals/new_project_modal.py`):**
  Implement `NewProjectWizardModal` with background worker tasks (`run_worker(..., thread=True)`).

### Phased Roadmap
1. **Phase 1 (Foundations & CLI Parity):** Define hookspec, implement creation in `sase-github` and `bare_git`, and expose `sase project add/create` CLI commands.
2. **Phase 2 (TUI Import Flow):** Implement `n` keybinding and Step 2A (GitHub Org Candidate Browser).
3. **Phase 3 (TUI Greenfield Creation):** Implement Step 2B (Create Form) and Step 3 (Provisioning Checklist).
4. **Phase 4 (Visual Polish & Golden Snapshots):** Add PNG visual snapshot tests under `tests/ace/tui/visual/test_ace_png_snapshots_config_center_projects.py`.

---

## 5. Artifact Snapshot

The full research report has been committed and registered as an audited artifact:
```bash
sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/admin_center_project_creation__gem.md" -l "research:202610/admin_center_project_creation__gem.md"
```
- **Artifact ID:** `explicit:b9db38cf2ea14f6d94c9ab79`
- **Stored Snapshot:** `~/.sase/artifacts/agents/gh_sase-org__sase/20261011085321/admin_center_project_creation__gem-135d4a486b00.md`
