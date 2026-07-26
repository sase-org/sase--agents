# Chat History - ace-run (chop.refresh_docs.sase.1_232033.1)

- **TIMESTAMP:** 2026-07-25 16:58:28 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.1_232033.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.1_232033.1, tribe=chop)
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

I'll start by getting oriented — understanding the repo's documentation surface, what checks exist, and what's changed since the last docs refresh.

Now let me find the last documentation refresh and what's changed since.

The last docs refresh was `bf1570adb` (Jul 24), 149 commits back. Let me survey what's changed since.

Substantial change surface. Let me start the environment install in the background while I dig into specifics.

Docs are well-maintained incrementally, so my job is finding the gaps. Let me verify the CLI reference against the actual CLI.

Let me check the highest-value gaps: the breaking model-alias change, wait priorities, and the placeholder store.

Confirmed gap #1. Let me verify the exact current behavior.

Runner slots are well-covered. Let me check the placeholder store, Chats pane, and sessions.

Let me systematically compare the full CLI surface against the reference doc.

Two commands are entirely undocumented. Let me check where they belong and examine the Chats pane.

Found a concrete doc error. Let me verify.

Now let me examine the ACE Chats pane, which shipped across many commits.

Let me gather the Chats pane's actual behavior in detail.

Let me check the remaining candidate gaps in a batch.

Found another gap — let me verify the wait modal's actual fields.

Let me establish a baseline docs build while I check a few more areas.

Now let me make the fixes. Starting with the stale `epic_creator` guidance.

Baseline docs build passes. Now the edits.

Now the incorrect command name in the artifact contract.

Now the `agent-cli` documentation in the provider guide.

Now the largest gap — the ACE Chats pane. Let me confirm the remaining details.

Now I'll write the Chats pane section.

Let me verify the filter-session claims I made.

Now the Wait Modal section, which is missing the Priority field.

Let me check the repo's verification targets and run them.

The formatter reflowed my tables. I see two more stale command references to fix.

The wrong command name appears in 5 docs. Let me fix all occurrences mechanically and verify.

Docs build passes. Let me verify the new anchors actually resolve in the built site.

All anchors resolve. Let me run the full repo check in the background while I review remaining areas.

The working directory persisted from my earlier `cd`. Let me correct that and check the background run.

The Admin Center's Agent CLIs tab is documented but had no CLI counterpart. Let me cross-link them.

Let me review my full diff while the check runs.

Let me correct that last claim — I misread the multi-value branch.

Let me do a final sweep for any other stale command names in the docs.

`sase sdd` appears in blog posts but isn't a real command. Let me check the context.

`just check` passed. Let me re-run the doc-sensitive checks to cover my latest edits.

Documentation refresh is complete. Only documentation files changed — no source, tests, or build config.

## What I found and fixed

I diffed the 149 commits since the last docs refresh (`bf1570adb`, Jul 24), then verified each suspected gap against the running CLI and the source rather than against the commit messages.

**Wrong command name (10 occurrences, 6 files).** Docs documented `sase artifact create`. That command does not exist — it is `sase artifact-file create`, and `sase artifact` is rejected by the parser. Fixed everywhere, including the `### sase artifact` heading in the configuration reference, and added the real `-k/--kind` values (`chat`, `plan`, `image`, `markdown`, `pdf`, `file`).

**`sase agent-cli` was entirely undocumented.** Zero mentions across the whole docs tree, despite being a substantial user-facing surface. Added an "Inventory and Updates" section to the agent-providers page covering `list`/`update`, the offline/refresh caching flags, and a table of what each install method does (npm, non-writable npm root, self-managed, Homebrew, bundled, unknown) — including that SASE never uses `sudo` and never guesses an update command. Added CLI-reference rows, a flag table in the configuration reference, and cross-links to the ACE Admin Center's Agent CLIs tab, which was already documented but had no CLI counterpart.

**Stale `epic_creator` guidance (breaking change).** `docs/llms.md` and `docs/configuration.md` still said legacy `epic_creator` entries "remain accepted so existing configs still load." Commit `14bf5f15c` retired it: the schema no longer describes it, and `sase doctor` now reports a leftover entry as a problem to delete. Corrected both, and noted `phase_worker` in the same breath.

**ACE Chats pane was undocumented.** The sase-90 series shipped a catalog-backed pane with a detail view, agent linking, and a filter grammar; ace.md mentioned it only in the sub-tab strip. Added a full section: the four provenance badges, the bounded 200-line detail preview, all nine keybindings with their keymap-action names, the `provenance:`/`machine:`/`project:`/`agent:`/`workflow:`/`since:`/`until:` grammar, and the fact that — unlike Commits and Plans — **Chats filters reject negation**.

**Wait Modal missing its Priority field.** ace.md listed three editable fields; the modal has four plus a read-only beads summary and a `Ctrl+R` run-now binding. The runner-slots troubleshooting page already referenced editing priority there, so the two pages disagreed.

**Non-existent `sase sdd` in two blog posts**, including a command cheat-sheet table. Replaced with the real `sase plan search` / `sase plan links validate` / `sase repo init`.

One correction to my own work along the way: I initially wrote that `s` returns a multi-value provenance filter to `All`; re-reading `cycle_provenance`, a multi-value selection is treated like `All` and the next press selects `local`. The published text says the latter.

## Verification

`just check` passed (exit 0), and `just fmt-md-check` plus `just docs-check` (strict mkdocs) pass against the final state. I confirmed the four new cross-reference anchors actually resolve in the built site rather than assuming they would.

## Suspected code inconsistency — not fixed, for someone else to pick up

Two user-facing install hints for OpenCode disagree. `sase doctor` prints `install from https://opencode.ai/docs` (`src/sase/doctor/checks_providers.py:37`), while `sase agent-cli` prints `npm install -g opencode-ai`, derived from `"package": "opencode-ai"` in `src/sase/llm_provider/opencode.py:155`. Both are workable instructions, but they come from independent sources that can drift. This matters for the docs because `docs/agent_providers.md` explicitly promises its snippets match the doctor hints, and its intro says only Claude, Codex, and Qwen install via npm — which the agent-cli metadata contradicts. I documented the doctor-matching behavior as-is and left the code alone; consolidating the two hint registries would be the real fix.

I made these changes in this session, so I'll commit them with the required skill.

Documentation-only change across 10 files. Writing the commit message.

Committed and pushed.

**`b0f491800` — `docs: refresh user-facing documentation`** (10 files, +242/−100)

Working tree is clean and `master` is in sync with `origin/master` — no ahead/behind marker. The `just fix` pre-commit hook ran clean. One benign warning: agent-hood publication is deferred and will retry automatically; the primary commit and push both succeeded.

The commit body records the substance of the refresh:

- **`sase artifact create` → `sase artifact-file create`** — 10 occurrences across 6 files; the documented command does not exist and is rejected by the parser. Added the real `-k/--kind` values.
- **`sase agent-cli` documented for the first time** — new "Inventory and Updates" section, CLI-reference rows, a flag table, and cross-links to the previously orphaned Admin Center Agent CLIs tab.
- **Retired `epic_creator` guidance corrected** — the docs claimed legacy entries still load; `sase doctor` now flags them for deletion.
- **ACE Chats pane documented** — badges, bounded preview, nine keybindings, filter grammar, and the negation restriction that distinguishes it from Commits and Plans.
- **Wait Modal Priority field added** — resolves a contradiction with the runner-slots troubleshooting page.
- **Non-existent `sase sdd` replaced** in two blog posts, including a cheat-sheet table.

I also carried the suspected code inconsistency into the commit body rather than only my response, so it survives in the history for whoever picks it up: `sase doctor` and `sase agent-cli` print different OpenCode install hints from independent registries (`checks_providers.py` vs. `opencode.py`). Both hints work, but `docs/agent_providers.md` promises its snippets match the doctor hints while its intro claims only Claude, Codex, and Qwen install via npm — which the agent-cli metadata contradicts. I documented the doctor-matching behavior as it actually is and left the code untouched; consolidating the two hint sources is the real fix.
