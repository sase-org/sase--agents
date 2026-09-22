# Chat History - ace-run (chop.refresh_docs.sase.5_808460.1)

- **TIMESTAMP:** 2026-09-21 21:33:48 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.5_808460.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.5_808460.1, tribe=chop)
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

Last refresh: `ea6fc5918d` (2026-09-19). Let's see what changed since.

Now I'll fan out research agents over the undocumented commit groups.

Now applying edits. Starting with `docs/notifications.md`.

Verified. Applying notifications.md edits.

Good — prettier will repad tables. Now ace.md notification edits.

Confirmed. Applying Services edits to ace.md and axe.md.

Notifications, Services tab, and detach-scope docs are updated. Next I'm updating the beads and Agents-tab docs.

Agents-tab edits are in. Now I'm doing the config, workspace, and agy provider docs, then running the formatter and docs build.

Now adding the agy header paragraph to configuration.md, then workspace/notify/bead tables.

The strict docs build and the prettier check both pass. Last step: making sure the new anchor links actually resolve.

Every anchor resolves. Because I changed tracked files, I'm required to read the lint/test memory next.

`just check` passed. Now the final declaration.

I updated 10 files under `docs/` to cover what landed since the last refresh on 2026-09-19 (`ea6fc5918d`). About 140 commits came in after it, and I checked each gap against the current code before writing about it. `just docs-check` (the strict mkdocs build), `just fmt-md-check` and `sase tool run check` all pass. Every new anchor link resolves in the built site. The commit is declared, and the host will create it.

**What changed:**
- **Services tab** (`ace.md`, `axe.md`):
  - The footer `SVC` pill section was stale and now describes current behavior: it shows running/desired counts (`N/M`), or a red `!` plus a `Services unhealthy` toast when something is wrong. The old RUNNING/STOPPED labels only show before the first status snapshot loads.
  - Documented the host line at the top of the info panel, and that the tab is now `services` with `axe` still accepted as an alias.
  - Corrected the quit menu: quitting stops only the `scheduler` service proc, and the service host keeps running.
  - The blue gear in the top bar no longer counts service procs.
- **Detached work** (`axe.md`, `architecture.md`, `configuration.md`): the list of processes that escape into their own systemd scope now includes hook, checks, mentor and workflow runners, file-hook batches, bead sync, and chat-install.
- **Notifications** (`notifications.md`, `ace.md`):
  - Added the recovery dialog for failed gates (`r` resume, `R` restart, `c` cancel, `e` error report).
  - Delivery rules now also apply to toasts, bells and snooze reminders.
  - The bell only rings inside tmux, and a sound player is stopped after 30 seconds.
  - Settlement notifications now mark Agents-tab rows unread.
- **Agents tab** (`ace.md`): the new `Beads` part of the ARTIFACTS lane, the orange `?N` chip on clan rows waiting on unknown targets, panel focus following the selected agent after a refresh, and the preview reader sizing itself to its content.
- **Beads** (`beads.md`, `configuration.md`):
  - When an agent runs `sase bead show`, it now logs a `viewed` touch.
  - Added a glyph legend for touched beads and documented the touch index with its `beads.touch_index` doctor check.
  - Added a flag table for `sase bead touched`.
- **Usage and misc** (`agent_providers.md`, `configuration.md`, `llms.md`, `plugins.md`, `workspace.md`):
  - Documented how agy's four usage windows show in the header, and that short header labels drop the `family:` prefix.
  - Fixed two links in `agent_providers.md`, each labeled "subscription usage": the Muse one pointed at its own section and the agy one pointed at Muse's.
  - Added a `sase notify rules` row, a `sase update -v` example, and the new wording of workspace-preparation errors.

**Suspected code bug (not fixed):** the `sase bead touched` help text in `src/sase/main/parser_bead_touched.py:30` says `viewed` comes from "human `show` views". In fact views are recorded only when an agent runs the command (`src/sase/bead/bead_views.py:87-90`), so "human" should probably say "agent". The CLI snapshot `tests/completion/snapshots/cli_spec.json` probably stores that wording too. I noted this in the commit message.
