# Chat History - ace-run (chop.refresh_docs.sase.5_458602.1)

- **TIMESTAMP:** 2026-10-13 01:45:08 EDT
- **MODEL:** grok/grok-4.7
- **AGENT:** chop.refresh_docs.sase.5_458602.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.5_458602.1, tribe=chop)
%queue(capacity=1)
Refresh the documentation for sase.

Review the current repository behavior and the changes since the last documentation
refresh. Update user-facing documentation so it is accurate, complete, and clear to
someone new to the project. You may only create, modify, or delete documentation
files, such as Markdown or other docs-tree content, READMEs, and doc-adjacent assets.
You MUST NOT create, modify, or delete source code, tests, build configuration, or any
other non-documentation file, even to fix a bug you are confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I'll refresh the user-facing docs against the current repository behavior and the changes since the last documentation pass. First I'm locating the docs tree, the last refresh, and how documentation checks run.

The feature commits already updated most guides. I'm correcting the places that still disagree with the current Projects keymap, Archive restore flow, New Project wizard, and Node Finder.

The documentation refresh is partway through. I'll finish the remaining user-facing edits, then run the docs checks.

The Projects keymap and Archive sections are in place. I'll align the CLI and project-spec pages with the same behavior, then add the short new-user pointers.

User-facing docs now match the current Projects, Archive, and record behavior. `just docs-check` passed.

The refresh covers six guides:

- **Projects keymap.** `docs/configuration.md` had two `ace.keymaps.projects` sections. The short duplicate is gone. The remaining map says which keys work on Projects versus Repos and Workspaces, including `n` for the New Project wizard and `s` to reveal a project the current filter is hiding.
- **New Project wizard.** `docs/ace.md` records the suggest groups, source keys, the under-30-row detail collapse, Review and Failed navigation, and `+` / `=` on the Ready stage. Getting Started points at Admin Center `#`, Projects `5`, then `n`.
- **Adding projects.** `sase project suggest --all` includes sidecars, forks, archived repositories, enabled projects, numbered clone copies, and third-party local checkouts. `add` and `create` take `-Q`/`--request-path` and `-R`/`--result-path`, defaulting to `$SASE_PROC_REQUEST_PATH` and `$SASE_PROC_RESULT_PATH`.
- **Agents Archive and Node Finder.** The Archive chooser documents restore (no new run), the `⌂ restored` suffix, chooser-only restore-and-show, list-level fork and read keys, and the live-only toasts. Node Finder's `◷ In Archive` section and the RECORD deck cards are described from the current UI.

`sase tool run check` failed on one test that does not depend on these docs. `test_path_label_exemptions_name_existing_sites_and_rationales` still exempts `src/sase/ace/tui/modals/revive_agent_modal.py` `_agent_filter_label` `Path(agent.project_file).parent.name`, but that file was removed in `ba89d2a6db` (`refactor(ace): remove Archive flag residue and lazy-load grouping`). The exemption is stale. It was left unfixed because this job may only change documentation.
