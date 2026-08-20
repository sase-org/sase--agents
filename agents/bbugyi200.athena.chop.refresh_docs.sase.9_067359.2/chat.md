# Chat History - ace-run (chop.refresh_docs.sase.9_067359.2)

- **TIMESTAMP:** 2026-08-20 00:22:01 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** chop.refresh_docs.sase.9_067359.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.9_067359.2, tribe=chop)
%wait:chop.refresh_docs.sase.9_067359.1
%wait(runners=0)
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

I'll start by locating the update agent's documentation changes and checking them against current system behavior before editing any docs.

I'll record the patch/chat skills and inspect git history plus the current patch so I can isolate the update agent's docs.

The update work is the docs-refresh commit on master. I'll inspect that commit and the related agent chat next.

The update agent is `.1` on this chop; I'll pull its transcript and the full docs diff, then check how docs are validated.

I'll pull the full docs diff and yesterday's inspect-agent pattern so this review can match the same verification bar.

I’ll pull the remaining large diffs and start checking the update agent’s claims against the live CLI and source.

I'll read the glossary terms and verify the highest-risk CLI and ACE claims against live help and source.

The CLI claims look solid so far. Next I’ll check ACE tab numbers, filter-bar persistence, and the remaining user-facing wording against source.

The update agent’s facts mostly match the code. I’ll fix a few accuracy slips and the workflow-order wording that would trip a new user.

Edits are docs-only. Next I’ll install the workspace and run the documentation checks.

The update agent’s refresh (`3078146fe`, `chop.refresh_docs.sase.9_067359.1`) mostly matches current SASE behavior. I re-checked every changed claim against live CLI help, default config, and source, then tightened a few places that were still wrong or easy to misread.

## What held up

The high-impact corrections were already right:

- Default `sase agent list` is **running only**; `-a` adds recent DONE/FAILED (50 per project). `sase agent kill` requires `-n/--name`.
- `sase monitor start` takes the command after `--`. `-s`/`-S` are required; `-r` defaults to `run command` and `-t` to `1h`. `-c/--command` is a hidden alias.
- Artifacts filter bars stay on screen. Files kind-cycle is `z`. Admin Center tabs are Config `1`, Logs `2`, Procs `3`, Projects `4`, Statistics `5`, Updates `6`, XPrompts `7`.
- Monitor rows have no left-side title; identity is the right-hand `%id`.
- Current project is MRU-derived, not cwd-derived. Beads `due:` / `has:+1` / `has:reopened` exist. Axe ships six default lumberjacks. `model_tier_map` is schema-valid and unread.

## What I changed

**Accuracy**

1. **Query language mixed panes.** The refresh said Beads/Plans/Files share the idle filter row, then kept “previews against the already-loaded Patch snapshot.” Other panes preview their own snapshot. Split that.
2. **`limit:0` is not Stitches-only.** The shared host parser treats `limit:0` as unlimited on every pane; completions still offer `all`, not `0`.
3. **CLI index is not “every subcommand.”** Compact `sase --help` lists 13 common commands; `docs/cli.md` is a discovery index. Getting Started now says that, and notes that compact help’s `agent` blurb (“active and recent”) is not the list default.

**Workflow order / new-user traps**

4. **Monitor family diagram.** It showed the follow-up (`acme--1`) already RUNNING right after `sase monitor start`. The follow-up starts only after the command settles as `completed`/`failed`/`timeout`, and only with `--next`. Split into “right after start” vs “after the command finishes.”
5. **Waiting for DONE.** Default `sase agent list` drops a row when the run ends. Getting Started now says to poll `-a` (or ACE) until the status is `DONE`/`FAILED`; `-a` still includes running agents.
6. **`-n` means three different things.** Kill: `--name`. Restart: `--dry-run` (name is positional). Monitor start: `--next`.
7. **Current project.** Lead with “the project you most recently launched on,” then the MRU mechanism. After the first `#git:home` run, ACE’s chip is `+home`.
8. **`due:`.** It matches flag beads (feature-flag removal tasks). A positive `due:` hides other bead types.
9. **Admin Center Updates.** `#` opens **home** first, then `6` enters Updates. `,U` still cannot install plugins.
10. **Patch expansion hint.** Launch still prints `sase patch show`, which is not a command. Docs now say not to run it.

## Suspected code bugs (not fixed)

These are real; docs now describe actual behavior:

1. **Patch `@` expansion invents `sase patch show`.** `src/sase/artifact_providers/builtin_entry_patch.py` still emits that hint; argparse has no `show` subcommand. Use ACE Patches, `sase patch search`, or `sase patch current`.
2. **`llm_provider.model_tier_map` is dead config.** Schema accepts `large`/`small`; nothing reads them.
3. **The `/sase_monitor` skill still teaches hidden `-c/--command` and required `-r`/`-t`.** User docs match `--help`; the generated skill was left alone.
4. **Hardcoded Files bindings disagree with config.** `bindings.py` still maps `s` to `files_cycle_kind`; shipped `default_config.yml` and runtime use `z`.

## Checks

`just fmt-md-check`, `just docs-check` (mkdocs `--strict`), `just docs-pdf-check` (784-page handbook), and `just check` all passed. Only documentation files were changed. I have not committed.

I'll commit the documentation-only changes with the git-commit skill, then give a concise summary of what landed.

I'll record the commit skill, inspect the dirty docs, and write a conventional `docs` message from that diff.

The diff is docs-only and matches this inspect pass. Next I’ll write the conventional commit message and run the stitch.

The commit is still running; I’ll wait for stitch create to finish rather than ending the turn.

Committed the inspect-agent documentation fixes as `e6672413f` (`docs: correct inspect-agent findings in SASE user docs`) and pushed to `master`. The working tree is clean and in sync with `origin/master`.

The commit covers the accuracy and new-user wording edits only: mixed-pane query snapshots and `limit:0`, the monitor family timeline, running-only `sase agent list` / `-a` polling, the three meanings of `-n`, current project as MRU, `due:` on flag beads, Admin Center Updates key order, compact `--help` vs the CLI index, and the bogus `sase patch show` hint.

Suspected code bugs were recorded in the commit body, not fixed: Patch `@` expansion invents `sase patch show`; `llm_provider.model_tier_map` is unread; `/sase_monitor` still teaches hidden `-c` and required `-r`/`-t`; Files kind-cycle is `z` in config but `s` in `bindings.py`.

Primary commit succeeded; agent-hood prompt archive publication was deferred because the agents sync lock was busy (41 quarantined requests already). That does not affect the git commit.
