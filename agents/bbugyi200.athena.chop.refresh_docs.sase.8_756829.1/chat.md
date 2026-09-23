# Chat History - ace-run (chop.refresh_docs.sase.8_756829.1)

- **TIMESTAMP:** 2026-09-22 23:19:08 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.8_756829.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.8_756829.1, tribe=chop)
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

I'm reviewing the ~110 commits since the last docs refresh (2026-09-21). The largest undocumented change is the new `+project` tag feature. Next I'll find which doc files cover each area.

Launching four parallel investigators, each owning a separate set of doc files, to check the undocumented commits against the code and update the docs.

All four finished. Next I'll apply the edits they proposed for files outside their ownership, after checking them.

Now applying the cross-file edits.

Applied the cross-file edits. Now checking whether `sase project` accepts `+name` before documenting it in cli.md.

Formatting is clean. Next I'll run the strict MkDocs build and the generated-docs check.

MkDocs strict build passes. Running the repo check through `sase tool run`.

sase-16l already covers this failure. Adding my corroboration.

Spot-checking a couple of the agents' config claims against the code.

All changes are docs-only. Now submitting the final declaration.

I've refreshed the docs for the ~110 commits since the last refresh on 2026-09-21. 24 docs files changed (685 lines added, 294 removed), no code was touched, and the host will commit the result.

**Checks:** the strict docs build (`just docs-check`) and the Markdown formatting check both pass. The full `sase tool run check` passed every gate except symvision. That gate fails on master too, over `delete_paths_in_background` in `src/sase/_linked_repo_workspaces.py`, which the docs don't touch. It was already filed as sase-16l, so I added my reproduction to it.

**What's newly documented:**
- **Project tags (`+sase`, the biggest gap):** a new "Project Tags" section in `docs/xprompt.md` covers:
  - the syntax, and how a tag expands to its full `#gh:…` reference when an agent launches;
  - what happens with disabled, unknown or ambiguous tags;
  - the one-target-per-agent rule;
  - `+` completion in the TUI and the editor plugin, and how tags display.

  Related updates cover case-insensitive unique project names, the reserved `home` name, and `sase project show +sase`. The completion and editor pages now say the `+` picker opens after any whitespace, `{` or `|`.
- **TUI:** how Enter on the Agents tab picks what to act on, and the new action chooser. Also the agent header panel labels, the fleet header row appearing only when there's a problem, `path:` filters matching by substring, the renamed `model:`/`project:` labels, and when dismissed remote requests come back.
- **Service host and scheduler:**
  - readiness warnings in `sase service status`;
  - the host keeping its last working config when a new one fails to load;
  - procs it gives up on staying stopped, with a notification;
  - restarts that wait for the new pid;
  - restart backoff, `monitor.tool_wrap`, and `sase service init -a`.
- **Workspaces, beads and `sase tool`:** workspace checkouts that repair themselves or get re-cloned, bead sync rolling back bad merges, and how `sase tool run` owns and cleans up processes.
- **Developer docs:**
  - raw `just check` is refused inside agent shells;
  - how `just fix-tui-screenshots` retries, votes, waits for its lock and reports exit codes;
  - what triggers a rebuild of the Rust extension;
  - the core-pin update's exit codes.

The editor features for project tags come from the latest sase-core commit, which is newer than the version pinned in `sase-core-revision.txt`. It's worth confirming that the released language server binary includes them.

**Suspected code bugs (not fixed, for someone else to pick up):**
1. `sase prompt run/edit -P` only replaces `#` references (`src/sase/prompt/cli_run.py`). Re-running a cancelled prompt that contains a `+sase` tag fails with "Only one workspace target is allowed". The TUI expands tags first, so it doesn't hit this.
2. Agents launched with `sase bead work` quietly re-enable a disabled project for a `+tag` (`src/sase/agent/launch_cwd_bead_work.py`). Every other launch path rejects the tag instead.
3. The service warning for a mismatched temp directory can never fire. `src/sase/service/platform.py:154` compares the current shell's environment with itself.
4. `fix-tui-screenshots` can silently overwrite a screenshot that someone edited on disk while its verification passes were running (`tests/ace/tui/visual/_visual_maintenance_salvage.py`). The recheck before applying was removed in 44cc2b74b.
5. Smaller ones:
   - If the notifications fail to load on the first Enter on the Agents tab, the press does nothing, even for a row whose only target is its PR (`_agent_enter_action.py:272`).
   - A `restart: on-failure` proc that exits cleanly raises a red "gave up" error notification.
   - The `act_on_agent` comment in `default_config.yml:732` is stale.
   - The `+` completion rules differ between shell completion and the TUI.
   - One branch in the project-tag catalog cache does nothing different from the other.
   - In CI, a screenshot update can wait up to 2 hours for a lock before refusing.
   - The `sase bead touched` and `tmux_ring_bell` issues from the last refresh remain.

The commit message lists items 1–4 but leaves out the `Co-Authored-By` line. I submitted it before noticing, and it can't be changed after submission.
