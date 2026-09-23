# Chat History - ace-run (toobig-5y.plugins_browser_install.0)

- **TIMESTAMP:** 2026-09-23 18:41:59 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5y.plugins_browser_install.0

## Prompt

%id(plugins_browser_install.0, clan=toobig-5y)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/modals/plugins_browser_install.py` file up into multiple files? Use your best
%wait:toobig-5y.startup_loads.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. The 902-line `plugins_browser_install.py` is now five modules, all under 500 lines:

- [plugins_browser_install.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/plugins_browser_install.py) (172) — facade: re-exports plus `PluginInstallActionsMixin`, which keeps `action_install` and the `_on_install_preview` dispatcher
- [plugins_browser_install_previews.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/plugins_browser_install_previews.py) (101) — preview dataclasses and `plan_install_preview` / `plan_install_many_preview`
- [plugins_browser_install_messages.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/plugins_browser_install_messages.py) (94) — summary, toast, and label helpers
- [plugins_browser_install_single.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/plugins_browser_install_single.py) (344) — `PluginSingleInstallActionsMixin` (single + marked-set flows)
- [plugins_browser_install_combined.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/modals/plugins_browser_install_combined.py) (379) — `PluginCombinedInstallActionsMixin` (mixed CLI + plugin flow)

Also updated the three proc-site inventory entries to the methods' new files. All existing imports (`plugins_browser_pane`, `operations`, `update`, `uninstall`) keep working unchanged through the facade.

Verification: `just fmt`, ruff, and whole-repo mypy pass; 56 targeted tests pass (install, combined-install, inventory, uninstall, marks). One note: `just check` stops at the `pyscripts` lint gate, but I confirmed that failure exists identically on the clean tree (stale `tools/` vs `tests/ace/tui/tools/` placement rule) — pre-existing and unrelated to this split.
