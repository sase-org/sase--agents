# Chat History - ace-run (research.4e.gem)

- **TIMESTAMP:** 2026-10-13 11:46:20 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4e.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_112927.md`

## Prompt

%id(gem, clan=research.4e)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4e.cdx`, `research.4e.cld`, `research.4e.grk`, `research.4e.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
think I would like to rename the sub-tabs on the "Artifacts" tab.

- We should name "Stitch" to "Commits", "Patch" to "PRs", "Bead" to "Bugs", "Plan" to
  "Plans", and "File" to "Files".
- The goal of this change would be to use a more common terminology to describe the
  different artifact tabs and pluralize the tab names (which seems more appropriate).
- I'm not sure if getting rid of the stitch/patch/bead tab names is the right call.

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

# Research & Evaluation: Renaming Artifacts Sub-Tabs in SASE

**Researcher:** `research.4e.gem`  
**Durable Snapshot:** `file:explicit:34571ffa65ea805307f7b406`  
**Research Report Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/artifacts_subtab_renaming_evaluation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/artifacts_subtab_renaming_evaluation__gem.md)  
**Registered Artifact Label:** `research:202610/artifacts_subtab_renaming_evaluation__gem.md`

---

## Executive Summary

The proposed plan suggests renaming the sub-tabs under the top-level **Artifacts** tab:
* **"Stitch"** $\rightarrow$ **"Commits"**
* **"Patch"** $\rightarrow$ **"PRs"**
* **"Bead"** $\rightarrow$ **"Bugs"**
* **"Plan"** $\rightarrow$ **"Plans"**
* **"File"** $\rightarrow$ **"Files"**

### Verdict & Core Critique
1. **Pluralization is an unequivocal win:** All top-level TUI tabs in SASE are plural (**Agents**, **Artifacts**, **Services**), and internal sub-tab identifiers are already plural (`stitches`, `patches`, `beads`, `files`). Pluralizing the visual presentation labels restores grammatical consistency across the TUI hierarchy.
2. **"Stitch" $\rightarrow$ "Commits" is an excellent change:** What the pane renders is literally the Git/Mercurial commit history via `CommitsPane`. A "stitch" in SASE refers specifically to an ordered entry inside a Patch specification, but users browsing this tab are inspecting repository commits. Calling this tab "Commits" improves clarity and aligns with the underlying Textual widget name.
3. **"Patch" $\rightarrow$ "PRs" is an architectural regression:** In SASE, a Patch is the local unit of change (`<key>.sase`). A Patch begins in `WIP` or `Draft` status purely on the local machine with **no Pull Request opened**. Furthermore, SASE supports non-GitHub workflows and local-only changes. Renaming "Patch" to "PRs" misleads developers into believing an unmailed local change has been published to GitHub. SASE previously migrated *away* from `prs` to `patches` for this exact reason.
4. **"Bead" $\rightarrow$ "Bugs" is a severe category error:** Beads are SASE's universal work-tracking primitives. They encompass **Plan beads** (architectures), **Epic beads** (multi-phase initiatives), **Phase beads** (sub-tasks of epics), and typed **Task beads** (of which `bug` is merely 1 of 6 built-in types alongside `feature`, `ci`, `flake`, `memory`, and `flag`). Calling this tab "Bugs" would mislabel epics and feature work as defects. SASE previously migrated *away* from `bugs` to `beads`.
5. **Recommended Synthesis:** Adopt the pluralized, domain-accurate tab labels:
   $$\text{Stitch} \rightarrow \mathbf{Commits}, \quad \text{Patch} \rightarrow \mathbf{Patches}, \quad \text{Bead} \rightarrow \mathbf{Beads}, \quad \text{Plan} \rightarrow \mathbf{Plans}, \quad \text{File} \rightarrow \mathbf{Files}$$

---

## 1. Historical Context: How SASE Arrived Here

### The August 2026 Singularization (`bd6167875c`)
Prior to August 13, 2026, the Artifacts tab labels were **already plural**: `Stitches`, `Patches`, `Beads`, `Files`, and `Plans`.

In commit `bd6167875c` (*"feat(ace): rename Artifacts sub-tab labels to singular form"*), the project deliberately renamed all visible sub-tab labels to singular:
```python
labels = {
-   "patches": "Patches",
-   "stitches": "Stitches",
-   "beads": "Beads",
-   "files": "Files",
+   "patches": "Patch",
+   "stitches": "Stitch",
+   "beads": "Bead",
+   "files": "File",
}
```
**Why was that change made?**
1. **Dynamic Document Provider Pluralization:** The previous logic naively appended `"s"` to any provider kind: `f"{label}s"`. When sidecars with non-count or collective nouns were added (notably the `@research` document provider), naive pluralization resulted in grammatically awkward labels like `"Researches"`.
2. **Terminal Real Estate:** The singular forms shaved characters off the sub-tab strip, delaying degradation into the `compact` and `micro` responsive tiers on 80-column terminals.
3. **Locking Test:** The change added `tests/ace/tui/test_artifact_tab_labels.py` with an explicit assertion:
   ```python
   assert all(not label.casefold().endswith("s") for label in labels.values())
   ```

However, singularizing the sub-tabs created a subtle UX inconsistency:
- **Top-level tabs:** Plural (**Agents**, **Artifacts**, **Services**).
- **Internal IDs:** Plural (`stitches`, `patches`, `beads`, `files`).
- **Sub-tab display labels:** Singular (**Stitch**, **Patch**, **Bead**, **Plan**, **File**).

Pluralizing the tab labels resolves this friction.

### Previous Terminology Migrations: `prs` $\rightarrow$ `patches` and `bugs` $\rightarrow$ `beads`
The codebase retains backward compatibility mappings in `LEGACY_ARTIFACTS_SUBTABS` ([`_artifact_tab_model.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/_artifact_tab_model.py#L42-L50)):
```python
LEGACY_ARTIFACTS_SUBTABS: dict[str, ArtifactsSubTab] = {
    "prs": "patches",
    "bugs": "beads",
    "plans": "ref:plan",
    "other": "files",
    "chats": DEFAULT_ARTIFACTS_SUBTAB,
}
```
And in [`artifacts_navigation.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/actions/artifacts_navigation.py#L475-L485):
```python
def action_show_artifacts_prs(self) -> None:
    """Deprecated alias for action_show_artifacts_patches."""
    self._switch_artifacts_subtab("patches")

def action_show_artifacts_bugs(self) -> None:
    """Deprecated alias routing the retired Bugs sub-tab to Beads."""
    self._switch_artifacts_subtab("beads")
```
SASE historically **did** have "prs" and "bugs" sub-tabs! They were explicitly replaced because they no longer reflected what SASE does. Reverting back to them now would be a regression.

---

## 2. Critique of Each Proposed Tab Rename

| Current Label | Proposed Label | Recommended Label | Semantic Fidelity | Verdict |
| :--- | :--- | :--- | :--- | :--- |
| **Stitch** | **Commits** | **Commits** | Very High | **Strongly Endorsed** |
| **Patch** | **PRs** | **Patches** | Inaccurate | **Reject "PRs", Pluralize to "Patches"** |
| **Bead** | **Bugs** | **Beads** | Misleading / False | **Reject "Bugs", Pluralize to "Beads"** |
| **Plan** | **Plans** | **Plans** | Very High | **Strongly Endorsed** |
| **File** | **Files** | **Files** | Very High | **Strongly Endorsed** |

### 1. "Stitch" $\rightarrow$ "Commits" (Excellent)
* **What is actually rendered:** [`CommitsPane`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/widgets/artifacts/view.py#L238). It displays VCS commits across enabled projects with commit hashes, messages, author identity, timestamp, diffs, and repository context.
* **Why it works:** In SASE glossary definitions, a "stitch" is the internal numbered record inside a Patch specification (`STITCHES: (1) ...`). A user browsing this tab is looking at the repository commit log. Renaming it to "Commits" removes jargon while remaining factually true.

### 2. "Patch" $\rightarrow$ "PRs" (Harmful)
* **A Patch is not a PR:** A Patch is SASE's local unit of change (`<key>.sase`). Its lifecycle is $\text{WIP} \rightarrow \text{Draft} \rightarrow \text{Ready} \rightarrow \text{Mailed} \rightarrow \text{Submitted}$. In `WIP` and `Draft`, **no PR exists on GitHub or any remote forge**.
* **False operational assumptions:** Labeling this tab "PRs" implies every listed change is an active upstream Pull Request undergoing code review, when in reality most are local, unmailed working branches or agent draft specs.
* **Forge independence:** SASE supports non-GitHub backends and local-only changes.
* **Recommendation:** Pluralize to **"Patches"**. "Patch" is universally understood across Git, Linux, and Mercurial workflows without conflating local work with remote PRs.

### 3. "Bead" $\rightarrow$ "Bugs" (Critical Category Error)
* **Beads are the universal issue/work tracker:** Beads represent:
  * **Plan Beads:** Top-level architectural plans.
  * **Epic Beads:** Multi-phase engineering initiatives.
  * **Phase Beads:** Component phases executed by agents.
  * **Task Beads:** Discovered follow-up tasks (`bug`, `feature`, `ci`, `flake`, `memory`, `flag`).
* **Category Error:** "Bug" is only 1 of 6 task bead types. Calling the tab "Bugs" would mislabel major Epics and Feature implementations as software bugs, creating massive confusion.
* **Recommendation:** Pluralize to **"Beads"**. "Beads" is SASE's foundational metaphor for tracking work threads.

### 4. "Plan" $\rightarrow$ "Plans" & "File" $\rightarrow$ "Files" (Excellent)
* Documents in `plans/` are plans. Artifact files are files. Pluralizing both to **"Plans"** and **"Files"** is natural, clear, and standard.

---

## 3. Handling Document Providers & Pluralization

To avoid repeating the issue from August 2026 where naive string concatenation (`f"{label}s"`) turned `@research` into `"Researches"`:
1. **Explicit Spec Labels:** In [`builtin_plan_ref_provider_spec()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/artifact_providers/_builtin.py#L13-L51), explicitly define `"label": "Plans"`.
2. **Preserve Collective / Mass Nouns:** For sidecar document providers that do not declare an explicit plural label, use their title-cased `ref_kind` directly (`kind.title()`), allowing mass nouns like `"Research"` to render cleanly without forcing an unnatural `"s"`.

---

## 4. Implementation Strategy: Labels vs IDs

**Crucial Architectural Decision:** Change only the **visual presentation labels**, leaving internal identifiers (`stitches`, `patches`, `beads`, `files`, `ref:plan`) **strictly unchanged**.

* **Zero Breaking Changes:** Internal IDs are referenced across `default_config.yml`, `sase.schema.json`, persisted user session files, query history, TUI action methods (`action_show_artifacts_*`), and CLI subcommands (`sase artifact pane show stitches`).
* **Minimal Blast Radius:** Updating `descriptor.label` in [`fixed_descriptor()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/_artifact_tab_descriptors.py#L66-L95) and `builtin_plan_ref_provider_spec()` achieves 100% of the UI enhancement with zero technical debt or data migration.

### Responsive Width Impact
Across the sub-tab strip:
* **Current singular:** `1 ◉ Stitch │ 2 ⎇ Patch │ 3 ◈ Bead │ 4 ✎ Plan │ 5 ⚲ Research │ 6 ▤ File` (31 chars)
* **Proposed ("PRs"/"Bugs"):** `1 ◉ Commits │ 2 ⎇ PRs │ 3 ◈ Bugs │ 4 ✎ Plans │ 5 ⚲ Research │ 6 ▤ Files` (32 chars, +1)
* **Recommended:** `1 ◉ Commits │ 2 ⎇ Patches │ 3 ◈ Beads │ 4 ✎ Plans │ 5 ⚲ Research │ 6 ▤ Files` (37 chars, +6)

An addition of 6 characters across the entire width easily fits standard terminal widths and is gracefully handled by `PanelTabStrip`'s existing `full` $\rightarrow$ `compact` $\rightarrow$ `micro` responsive ladder.

---

## 5. Recommended Solution & Action Plan

Adopt the following sub-tab visual labels:
$$\mathbf{Commits} \quad \big| \quad \mathbf{Patches} \quad \big| \quad \mathbf{Beads} \quad \big| \quad \mathbf{Plans} \quad \big| \quad \mathbf{Files}$$

### Code Modifications Required:
1. **`src/sase/ace/tui/_artifact_tab_descriptors.py`**:
   Update `fixed_descriptor()` dictionary:
   ```python
   labels = {
       "patches": "Patches",
       "stitches": "Commits",
       "beads": "Beads",
       "agents": "Agents",
       "files": "Files",
   }
   ```
2. **`src/sase/artifact_providers/_builtin.py`**:
   Add `"label": "Plans"` inside `builtin_plan_ref_provider_spec()`.
3. **`tests/ace/tui/test_artifact_tab_labels.py`**:
   Update the test assertions to lock in the new plural labels.
4. **Docs & Help Modals**:
   Update `docs/ace.md` and related visual goldens.

---

*The full research report has been saved to disk and registered into the SASE artifact ledger under:*  
`sase artifact show file:explicit:34571ffa65ea805307f7b406` (`research:202610/artifacts_subtab_renaming_evaluation__gem.md`).

The finalizer declaration for `commit` has been successfully submitted and accepted for repository `sdd:research` (`repo-8caa19a02d02`), committing the research report `202610/artifacts_subtab_renaming_evaluation__gem.md` under commit message `docs(research): evaluate artifacts subtab renaming and pluralization`.
