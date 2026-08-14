# Chat History - ace-run (toobig-2p.split_file.src.sase.ace.tui.artifact_tabs.0)

- **TIMESTAMP:** 2026-08-14 18:49:02 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-2p.split_file.src.sase.ace.tui.artifact_tabs.0

## Prompt

#gh:sase-org/sase
%id:toobig-2p.split_file.src.sase.ace.tui.artifact_tabs.0
%clan(toobig-2p, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 766  src/sase/ace/tui/artifact_tabs.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/ace/tui/artifact_tabs.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by reading the file to understand its structure.

Now I have the full picture. Let me create the split modules.

Now the discovery module:

Now the descriptor-building module:

Now the facade:

Now the icons test and the contract harness:

Now the quickstart test, which references `artifact_tabs.fixed_descriptor`:

Now install and run the lint/test gates.

Done. `artifact_tabs.py` went from 766 lines to a 205-line facade, with the body split across three new private siblings:

| File | Lines | Holds |
|---|---|---|
| `src/sase/ace/tui/artifact_tabs.py` | 205 | Public API: caches, `resolve_artifacts_subtabs`, `normalize_artifacts_subtab`, `artifacts_pane_key`, `document_provider_roots`, `switch_to_artifacts_subtab`, compat constants, `__all__` |
| `_artifact_tab_model.py` | 131 | Type aliases, tab constants (accents/icons/pane ids/legacy map), and the frozen records |
| `_artifact_tab_discovery.py` | 271 | Walking project records → provider roots + discovery issues, plus the cache token |
| `_artifact_tab_descriptors.py` | 247 | Turning discovery output into `ArtifactsTabDescriptor` rows, accents, labels, icon sanitizing, digit shortcuts |

The public import surface is unchanged — every name previously exported by `artifact_tabs` still resolves there, so `app.py`, `widgets/artifacts/types.py`, keymaps, commands, and the action modules needed no edits.

Two things the symvision lint forced (it rejects private symbols imported across `src/` files), which is where the test churn comes from:

- Helpers now crossing a module boundary had to become public: `_fixed_descriptor` → `fixed_descriptor`, `_provider_descriptors` → `provider_descriptors`, `_assign_artifacts_digit_shortcuts` → `assign_artifacts_digit_shortcuts`, `_load_project_provider_records` → `load_project_provider_records`, `_provider_source_token` → `provider_source_token`, and the three records → `ProjectProviderRecord` / `ProviderDiscoveryIssue` / `ProviderLoadResult`. Helpers used only inside their own file (`_provider_accent_for_kind`, `_provider_label`, `_sanitize_tab_icon`, `_descriptor_for_provider_kind`, `_slug`, `_natural_label_key`, `_select_project_records`, `_load_workspace_provider_records`) stayed private.
- Two tests monkeypatched module globals that moved: `list_project_records` now patches on `_artifact_tab_discovery`, `cell_len` on `_artifact_tab_descriptors`.

`just check` is green — all lint gates plus the test lane, which escalated to the full suite (`rules: core-identity-changed`) and passed.

I'll commit the changes I made in this session using the commit skill.

Committed and pushed. Let me verify the affected tests still pass on the rebased tree.

Committed as `a09a5c129` and pushed; working tree is clean and `master` is in sync with `origin/master` (the commit rebased cleanly onto an upstream commit that landed meanwhile).

**What the commit contains** — the `artifact_tabs.py` split you asked for:

| File | Lines | Holds |
|---|---|---|
| `src/sase/ace/tui/artifact_tabs.py` | 205 | Public facade: caches, `resolve_artifacts_subtabs`, `normalize_artifacts_subtab`, `artifacts_pane_key`, `document_provider_roots`, `switch_to_artifacts_subtab`, compat constants, `__all__` |
| `_artifact_tab_model.py` | 131 | Type aliases, tab constants (accents/icons/pane ids/legacy map), frozen records |
| `_artifact_tab_discovery.py` | 271 | Project records → provider roots + discovery issues, cache token |
| `_artifact_tab_descriptors.py` | 247 | Discovery output → `ArtifactsTabDescriptor` rows, accents, labels, icon sanitizing, digit shortcuts |

Down from 766 lines, all four well under the 500-line target. The public import surface is unchanged, so `app.py`, the artifacts widgets, keymaps, commands, and action modules needed no edits. Test churn comes from symvision's rule against cross-file private imports: helpers crossing a module boundary became public (`fixed_descriptor`, `provider_descriptors`, `assign_artifacts_digit_shortcuts`, `load_project_provider_records`, `provider_source_token`, and the three records), and two tests now monkeypatch relocated globals on their new modules.

**Verification:** the pre-commit `just fix` hook ran clean, and I re-ran the six affected test files plus the artifacts contract suite against the rebased tree — 45 passed. The full `just check` (all lint gates plus the test lane, which escalated to the whole suite) was green earlier in this session, before the upstream commit was rebased in; I did not re-run the exhaustive lane after the rebase.
