# Chat History - ace-run (chop.refresh_docs.sase.3_793778.1)

- **TIMESTAMP:** 2026-09-27 03:46:56 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.3_793778.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.3_793778.1, tribe=chop)
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

I'm checking which recent code changes the docs don't cover yet, starting with the dispatch and turn-rename commits.

I'm auditing the docs against the code; the diff since the last refresh is small, so I'm running a wider accuracy check in parallel.

The audits found about 35 candidate doc errors. I'm checking each against the code before editing, starting with the Prompts overlay.

Now verifying the History behavior from a Stash entry point and the `,.` preconditions.

Prompts findings confirmed. Applying the `docs/ace.md` edits now.

Now the remote dispatch findings.

Dispatch findings confirmed. Editing `docs/remote_dispatch.md` and `docs/mobile_gateway.md`.

Now the named-proc / hold findings.

Still checking the hold and named-proc findings; next I'll verify the CLI TTL parsing and then edit.

Confirmed. Applying the procs/holds/`%queue` doc fixes.

I'm adding the missing `sase tool` rows to `docs/cli.md`, then moving on to the onboarding fixes.

Onboarding findings confirmed; applying them to README, INSTALL, getting_started, index, and init docs.

Now the draft blog post's stale spots.

Checking the mobile runbook's gateway-start claim, then formatting and running the docs checks.

Formatting is done. The repo requires reading its lint/test memory note before finishing, so I'm loading it now.

Running the docs build check and the repo check.

I refreshed 16 documentation files (only Markdown), and the host has accepted the commit. `just docs-check` passed. `just check` failed on 4 mypy errors in two Python files I didn't touch (`agent_groups/_tree.py` and `_agent_display_hint_sections.py`); the previous docs refresh reported the same errors.

Only three code commits landed since the last docs refresh, and the docs already covered them. So I checked four areas that changed a lot recently against the actual code and CLI `--help` output, and confirmed each finding before editing.

**What I corrected:**
- **Prompts overlay** (`docs/ace.md`):
  - The Trash demo used the wrong tab keys. Tabs go Stash → History → Trash, so `[` from Stash reaches Trash.
  - With `trash_limit: 0`, discarding a Stash draft deletes it permanently, and a partial discard has no confirmation.
  - Added when the overlay stays open or closes after a discard.
  - If the stash store can't be read, the History entry points open nothing either.
  - History opened from a Stash entry point loads prompts into the bar and never launches them.
  - `,.` needs a previously launched VCS xprompt, and `,Ctrl+G` goes straight to `$EDITOR`.
- **Remote dispatch and mobile gateway:**
  - `%dispatch` also rejects `%hold`.
  - Under the service host, the `mobile_gateway.agent_bridge_command` setting is ignored.
  - Remote rows use the normal `x` (stop), `R` (retry) and `F` (fork) keys.
  - Added the `sase machine agent` and `sase machine attention` commands, how they match an agent and when they exit 0.
  - The acceptance window comes from `-t`, else the configured request timeout, never under 30 seconds.
  - Added the mobile bridge's `fork-agent` and `retain_for_retry`.
- **Procs, holds and tools:**
  - A fully qualified named proc is written `<agent>--<name>`; the docs said `agent/name`.
  - `sase agent hold create` accepts positional selectors, and its `-T` only takes single-unit durations like `2h` (not `1h30m`).
  - Holds armed by a `%proc` end when that proc finishes.
  - `%queue` multipliers allow at most two decimal places.
  - Noted the old `proc-shell` spelling alongside `named-proc`.
  - Added the missing `sase tool wait`, `stop`, `failures`, `-H`, `-k`/`-x` and `-F` entries.
  - Replaced leftover "shell" wording with "turn" in `axe.md` and `llms.md`.
- **Onboarding** (README, INSTALL, getting started, index, init, draft blog post):
  - Muse can be picked automatically through the shipped size aliases.
  - Fixed where the project chip and the Projects tab are, and the name of what gets restarted after an update (the scheduler service proc).
  - Added `sase init --diff`.
  - Described what `sase memory read` accepts and the unaudited `sase memory show`.
  - `sase init service` applies immediately.
  - Explained how to copy the full artifact reference when the table cuts it off.
  - Gave the command to move a bead to `ready`.
  - Fixed several stale lines in the draft blog post.

**Suspected code bugs (not fixed, also listed in the commit message):**
1. **Named procs:** a find-and-replace from `proc-shell` to `named-proc` turned the old-spelling checks into no-ops (`procs/models/proc.py:96`, `procs/submission.py:354`, `agent/launch_proc_runtime.py:73`). The current Rust core still writes `proc-shell`, so procs whose supervisor died are never marked `error`. Also, `%proc` dispatch reports a failure after the proc has already started, and its hold is never rebound to the proc.
2. **Remote agent commands:** the `sase machine agent` lookup ignores which machine you named, so a same-named agent on another host could be targeted. It also only sends the first agent name as the query. Matching on a session id can hit several rows at once.
3. **Receipts:** in `dispatch/mutations.py`, a worker-unavailable error marks an already-accepted request as `unsent`, which invites a resubmission the docs forbid. Host errors also skip the same-key retry loop.
4. **`sase init service`:** it applies the change immediately, and `--diff` also writes the unit instead of only showing it.
5. **Prompts overlay:**
   - After lowering the trash limit, the Trash tab shows rows that were already evicted.
   - The empty-Stash hint says "switch with ]", but `[` is the key that reaches Trash.
   - Trash rows show raw project keys instead of display names.
   - Some help rows still say "stashed prompts panel".
6. **Help text:** still says "proc shell" in several places, `sase machine init` help claims piped stdin works (it doesn't), and `sase mobile agent-bridge --help` prints a literal `==SUPPRESS==`.

I didn't change `mkdocs.yml` because it's build configuration. Separately, 29 image-prompt Markdown files under `docs/images/` get built as orphan pages because nothing excludes them.
