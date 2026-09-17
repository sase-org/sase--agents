# Chat History - ace-run (chop.refresh_docs.sase.5_964679.1)

- **TIMESTAMP:** 2026-09-16 20:04:01 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.5_964679.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.5_964679.1, tribe=chop)
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

I'll start by getting oriented: the repo layout, the docs, and when the docs were last refreshed.

Next I'll find the last full documentation refresh and see how big the change range since then is.

The last refresh looks like `00d5c40a81` (2026-09-12) and `9c89ad770b` / `70d955dc51` (2026-09-11). Let me confirm what they covered and count the changes since.

293 commits since the last refresh on 2026-09-12. Let me list the user-facing ones (`feat`/`fix`/breaking) and check the docs tooling.

Many feature commits updated docs in the same change, so the gaps are mainly features that shipped without doc edits. Agent hold looks like the biggest one. Some quick greps to size the gaps:

The CLI runs from this checkout. Next, the Markdown formatter setup, so the agents' edits match the repo's wrapping style.

Prettier is configured with `proseWrap: always` and `printWidth: 88`. Next, doc sizes, so I can split files across parallel audit agents sensibly.

`ace.md` and `configuration.md` are huge, so each gets its own agent. A quick look at how `cli.md` is organized:

Only the CLI calls `arm_agent_hold` in Python. Arming could still happen inside a Rust launch binding, so I'll check how the launch path handles the `%hold` directive.

I'll align `cli.md`, `notifications.md`, `ace.md`, and `architecture.md` with the `%hold` caveat. First, the wording `xprompt.md` now uses:

Applying the caveat edits to all four files:

Whether `%queue(capacity=0)` is really rejected is decided in the Rust core. I'll check whether its binding imports in this venv, and what the tests pin.

The Rust extension isn't built in this workspace venv. The globally installed `sase` may have a working binding, so I'll try the check there (read-only).

Formatting accepts `capacity=0`, but parsing or validation might still reject it. Next, the parse side:

All eight docs agents have finished. I'm now fixing cross-file issues myself: the `%hold` caveat is done, and next is the invalid `wait_runners: 0` example in `axe.md`.

Now I'll fix the `axe.md` example and both field descriptions to match the current capacity-budget semantics.

The heading search found nothing, so `#queue-directive` might not exist. Checking the real heading and what `has_runner_threshold_directive` detects:

The "unless the prompt already authors its own `%queue` capacity" wording is correct. I'll locate the heading above the capacity section to get the right anchor.

That section has had no heading since before this refresh: the wait and queue text sits under "Launch-Scoped Model Alias Overrides". I'll find where the alias text ends so I can add a proper heading.

The name, wait, and queue content starts at line 2193. I'll add a heading there and a matching table-of-contents entry.

Next, the same `wait_runners` fix in `configuration.md`, plus the retired `%tribe:` mention and the `sudo answer` row in `cli.md`.

`%tribe` has been removed; its replacements are `%id(tribe=...)` and the `#tribe:` shorthand. I'll also check whether the bundled tribe config is keyed `job` or `chop`.

Before changing the `sudo answer` row, I'll verify the claim that `--resume`/`--restart` can't skip commands that already ran.

Confirmed: the root commands run before the retry option is applied, and the manifest resets `resume_from`. Updating the `cli.md` row:

Confirmed: the reaper reads those two keys only when a caller passes nothing, and every production caller passes the `disk.pressure` warn threshold. Adding that note to `configuration.md`:

Remaining optional items: the `dev-update` deadlines in `plugins.md` and the `#git:<name>` project reuse in `workspace.md`.

This paragraph is stale since `73e337ff27`: a claimed alias no longer auto-initializes a separate project. I'll check what `find_project_ref_owner` covers before rewriting it.

The resolver now checks claimed names and aliases before treating a name as new. Rewriting the paragraph to match:

Now the last optional item: a link from the `commit_hooks` config docs to the new hook-evidence section.

Prettier only reformatted doc files, and nothing outside the docs changed. Now running the repository's doc checks, starting with the strict mkdocs build.

The strict build passes. `mkdocs --strict` only flags broken anchors if `mkdocs.yml` enables anchor validation, so I'll check that and run my own anchor scan over the changed files.

`mkdocs.yml` has no anchor validation, and my slug heuristic may be wrong for headings with `<id>`-style text. The built site's HTML is authoritative, so I'll check each flagged anchor there.

All internal fragment links resolve. Next is the PDF handbook check, which may need to install Playwright/Chromium.

All four doc checks pass. The repo's lint/test note also requires `just check` whenever tracked files change, so I'll run it now. I'm skipping `just fix`, since it could reformat non-doc files.

`just check` exited 1 with 47 test failures, mostly monitor tests. Docs-only edits shouldn't break these, so I'll check whether the lint gates passed and what the failures actually are.

Every lint gate passed, including `sase validate`. The test failures look tied to the new systemd-scope escape (`--scope` argv differences) rather than to docs. Checking one traceback to confirm:

With the scope escape disabled, 46 of 47 pass, so they're sensitive to being run from inside a SASE systemd scope. Checking the one remaining failure:

This last one is a stale test reference rather than an environment problem. Confirming the missing file:

Both confirmed. A last hygiene scan of the added lines, for leaked local paths, workspace names, or agent scratch notes:

Docs work is done and checked. Last step is the SASE final declaration.

I refreshed 46 documentation files (the docs pages plus `INSTALL.md` and `CONTRIBUTING.md`) against the 293 commits since the last refresh on 2026-09-12. All doc checks pass, but `just check` failed: 47 tests fail, none because of these doc changes (details below). The commit request was accepted and the host will create the commit.

## Main documentation changes
- **Agent holds:** new `sase agent hold` section in `cli.md`, plus how holds appear in the TUI, doctor, notifications, config and troubleshooting.
  - **`%hold` doesn't work yet:** the directive is parsed, shown in launch previews and asks for confirmation, but submitting the launch never creates a hold; only the CLI does. The work to make it do so (bead `sase-11l.5.1.2`) is still in progress, so the docs now say this in every place that mentions `%hold`.
- **CLI and config reference:** checked against the full command tree and `default_config.yml`. Added missing commands, flags, config keys, environment variables and a feature-flag table; removed options that don't exist (e.g. `repo init --path`).
- **AXE:** consistent routine/job terminology, the missing jobs, and schema version 2 for `status --json`. Fixed the example `wait_runners: 0`: it becomes `%queue(capacity=0)`, which is rejected at launch.
- **Other areas:**
  - rewrote `sudo.md` and the Commit Workflows overview;
  - bead lookups across projects;
  - the new mandatory keep/close bead action on commits;
  - git network retries for SDD sidecar clones;
  - TUI keys, the Refresh panel and remote fleet rows;
  - line-addressed links in the pager;
  - Codex and Claude provider safeguards.
- **Structure:** added a heading for the wait/queue section of `xprompt.md` (it had none) and fixed broken anchors.

## Checks
- **Doc checks pass:** `docs-check` (strict build), `docs-pdf-check` (941-page handbook), `docs-deploy-artifact-check`, and the prettier format check. A scan of the built site found no broken internal links.
- **`just check`:** all lint gates and `sase validate` pass. The Rust core got rebuilt during the run, so the test lane expanded to the full suite: 47 failed, 42,399 passed.
  - 46 fail only because this agent runs inside a SASE systemd scope; they pass with `SASE_DETACH_SCOPE_DISABLE=1`, so those tests don't isolate themselves from that environment.
  - 1 is a real failure already on master: `tests/test_proc_env_isolation.py:53` still names `tests/test_config.py`, which the recent config-test split removed.

## Suspected code bugs (not fixed; also listed in the commit message)
Confirmed by reading the code:
1. `src/sase/ace/restore.py:218` passes a name to `sase stitch create`, which takes no positional argument, so `sase restore` fails at its last step.
2. `sase stitch create -s/--status` is ignored; the handler never passes it on.
3. `sase sudo answer -r/-R` can't skip commands that already ran: the commands run before the retry option is applied, and `sudo/manifest.py:80` resets the resume point.
4. `managed_tmp.pressure.min_available_bytes` and `recovery_available_bytes` have no effect: every production caller passes the `disk.pressure` warn threshold instead.

Reported by the audit agents, not re-checked by me:
5. `sase run` skips the broad-hold confirmation for project-scoped `pending` holds.
6. The `agent_holds.stale` doctor check prunes holds and sends notifications, although doctor is meant to be read-only.
7. A user's `tasks.history_limit` never takes effect because the `procs.history_limit` default always wins.
8. Monitor follow-ups drop the starter's `%auto`, priority and capacity settings.
9. Hidden subcommands show up as `==SUPPRESS==` in `sase axe --help` and `sase stitch --help`.
10. `sase tui --profile` help names the wrong default path.

I didn't file task beads for these, since you asked for them to be described here instead.
