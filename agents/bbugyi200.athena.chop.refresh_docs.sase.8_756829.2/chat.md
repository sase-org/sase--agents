# Chat History - ace-run (chop.refresh_docs.sase.8_756829.2)

- **TIMESTAMP:** 2026-09-23 02:26:47 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.8_756829.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.8_756829.2, tribe=chop)
%wait:chop.refresh_docs.sase.8_756829.1
%queue(capacity=1)
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where terminology or
workflow ordering could be misunderstood. You may only create, modify, or delete
documentation files, such as Markdown or other docs-tree content, READMEs, and
doc-adjacent assets. You MUST NOT create, modify, or delete source code, tests, build
configuration, or any other non-documentation file, even to fix a bug you are
confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

All five review agents are done. Next I'll review their combined doc diff and run the repo's doc checks.

Now I'm running the doc checks: prettier, the Patch/stitch terminology audit, and the strict mkdocs build.

Consistent with the rest of the guide. I'll restore the explicit `#2` and above in the self-heal sentence, because "those same" makes a new reader look back for the antecedent.

Now I'm reading through the combined diff to spot-check what the agents changed.

One thing looks inconsistent: xprompt.md still mentions a "top-bar current-project chip", but the ACE agent says that chip moved. I'm checking the layout code.

Fixed that. Next I'm running the final doc checks, then the repo's standard `sase tool run check`.

The only failure is symvision on a Python source symbol. I'm confirming it's the known pre-existing master failure.

I checked every claim the docs-update agent changed in commit `07d867e61` (24 files) against the code at HEAD, including the Rust code in sase-core. I corrected the wrong or unclear ones in 20 docs files; nothing outside the docs was touched. The commit has been declared and SASE will create it.

**Checks:** prettier, the Patch/stitch terminology audit and `mkdocs build --strict` all pass. `sase tool run check` passes every step except symvision. That step fails on a Python function (`delete_paths_in_background` is flagged as unused). It already fails on master and is tracked as bead `sase-16l`, so my changes didn't cause it.

## Main corrections
- **Broken table:** a bare `|` in `docs/editor.md` split a row of the language-server table across three columns. It's now escaped.
- **Project tags (`xprompt.md`, `prompt.md`, `completion.md`, `project_spec.md`):**
  - Picking a completion row doesn't remove every other workspace target in the segment. It removes only other known `+tags` and `#` refs at the start of a line.
  - An unknown tag's error always lists up to three suggestions, so the example was wrong.
  - A tag can also match a project's directory key or alias.
  - `sase bead work` skips tag checks and re-enables disabled projects.
  - The `-P` prefix only replaces a `#` ref at the start of a line; otherwise it adds the new prefix in front.
  - A few tag-spelling and completion-filter rules were missing.
- **ACE (`ace.md`, `remote_dispatch.md`, `notifications.md`):**
  - The machine-issue count counts problems, not machines.
  - The current-project chip moved out of the top bar into each tab's status row. This was also out of date in `xprompt.md`.
  - The `load:` gauge is in the Agents status row, not the header.
  - Some details of how remote notification rows come back and when they settle were wrong.
- **Service and scheduler (`axe.md`, `configuration.md`, `monitors.md`, `init.md`, `cli.md`):**
  - `restart: on-failure` is a `service.procs` setting, not a systemd line.
  - Added the real backoff and crash-loop thresholds, what counts as a clean exit, and how a parked proc comes back.
  - The `tool_wrap` table was in the wrong order.
  - The temp-directory warning fires in the opposite direction from what the docs said.
  - `Source:` paths now point to the new `_settings_*.py` modules.
- **Development (`development.md`, `rust_backend.md`, `README.md`):**
  - Corrected `fix-tui-screenshots`: when it checks for golden edits made during a run, voting, exit codes in check mode, and where `-n` can go.
  - Added that the recipe guard lets commands through when `sase` isn't installed.
  - The core-pin ratchet also exits 3 when the pin file is missing or malformed.
- **Workspace and projects (`workspace.md`, `beads.md`, `sdd_storage.md`, `getting_started.md`):**
  - The `project.name_collisions` doctor check covers less than the docs said.
  - The self-heal fetch-and-rebase step runs only for the default branch.
  - Corrected what leads to `setup_workspace_failed`.

## Suspected code bugs (not fixed)
1. `service/platform.py` `_managed_tmpdir_root_warnings` compares the shell environment with a copy of itself, so the warning never fires.
2. `sase prompt run/edit -P` doesn't expand `+tags` first, so replaying a cancelled prompt that has a tag fails with "two targets".
3. `sase bead work` skips tag checks and re-enables disabled projects (`agent/launch_cwd_bead_work.py`).
4. Agent panels show disabled projects' refs as `+tags`, so relaunching those prompts is rejected, where the original `#` ref would have re-enabled the project.
5. `project.name_collisions` never compares directory keys with each other or with the reserved `home`. Its code comment says it does.
6. `fix-tui-screenshots` doesn't re-check golden edits after verification, so it can overwrite edits made during a run.
7. Pressing Enter on a pending gate that is still running shows "This gate already settled (pending)".
8. Remote notification polling fetches only one page of 100, so on a host with more pending requests, missing ones never settle.
9. The `act_on_agent` comment in `default_config.yml` still says "when both apply"; the chooser opens whenever two or more targets apply.
10. Possible, not tested: in the `rust-install` cached-wheel branch, a failed install can still be stamped as fresh.
11. Minor: a `start` request for a proc that is already running resets its restart history, clearing its crash-loop and alert state.
