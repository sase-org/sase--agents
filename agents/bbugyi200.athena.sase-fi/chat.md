# Chat History - ace-run (sase-fi)

- **TIMESTAMP:** 2026-08-06 16:33:01 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-fi

## Prompt

#gh:gh_sase-org__sase #commit
%id(sase-fi, bead=sase-fi)
%m:@medium_phase_worker
Can you complete the work for task bead sase-fi? The bead is already reserved for you and assigned to your
agent name: it was set to status=in_progress by the launch that started you; do not set the status by hand. Run
`sase bead show sase-fi`, read the description and notes, do the work, and close the bead with
`sase bead close sase-fi --note "<what you verified>"`. If you discover genuinely distinct follow-up work,
do not expand this bead's scope: use `/sase_new_task` to check duplicates and active epics, then record it in the
location that skill selects.

## Response

I'll start by looking at the bead.

Now update `commit_publication_transaction.py` to use the shared helper.

Now the full-sync path in `git_sync.py`.

Now add the helper and imports in `git_sync.py`.

Now add the `_restore_deferred_prompt_archives` helper.

Now update `git_sync.py` to thread the failures through.

Now wire the caller in `sync_agents`.

Now the commit-time message in `workflow_publication.py`.

Now the full check.

Done. `sase-fi` is closed.

## What was actually broken

The bead described the prompt archive as having no durable retry at all, but the real gap was narrower and worse-behaved: `publish_prompt_archive` *does* enqueue an agent-hood outbox request before touching the lock, and the commit-time drain (`_prepare_prompt_archive_retry`) *does* rebuild the deferred archive. The hole was the full-sync path — `sync_agents` acknowledged a queued request as soon as `agents/<global>/README.md` materialized, while `_integrate_export_pass` never rebuilt the prompt. So `sase agent sync -p sase` cleared the request and took the owed prompt with it. That matches the reported symptom exactly: sase-fa.4/.5 vanished after a later successful sync.

## Changes

- **`src/sase/agents_sync/prompt_archive/deferred.py`** (new) — the drain's prompt-archive retry, extracted so both paths share it; adds a non-raising `restore_deferred_prompt_archives` that reports per-request failures keyed by logical key.
- **`commit_publication_transaction.py`** — now uses the shared helper instead of its private copies.
- **`git_sync.py`** — the full sync's export pass builds the inventory once, passes it to hood reconciliation, and rebuilds the archives owed by the requests it is about to acknowledge. A request whose archive could not be rebuilt is *not* acknowledged and, unlike a non-materializing page, stays retryable rather than being retired.
- **`git_sync_transaction.py`** — stages `prompts`/`artifacts` in the sync commit and cleans them alongside the payload at both transaction boundaries.
- **`workflow_publication.py`** — a prompt archive that could not even be queued now fails the step with a `sase commit --resume` hint (matching agent-hood publication) instead of a dropped warning; a deferred one warns that it retries with agent publication.
- **`docs/agents_sidecar.md`** — documents that the hood request carries the prompt.

## Verification

`tests/agents_sync/test_deferred_prompt_archive.py` drives a genuine lock-busy defer over real git sidecars, then asserts the archive reaches the remote on the next sync and only then is the request acknowledged; a second test asserts an unrebuildable archive keeps the request queued and non-terminal. I confirmed both fail without the fix. Two new commit-workflow tests cover the queued and unqueueable messaging.

`just check-full` passed except two tests that also failed for reasons unrelated to this change and pass in isolation: the bead mutation-lock one is already fixed on `origin/master` by `5a1980363` (my checkout is 6 commits behind), and the ACE TUI codeblock-highlight one I recorded as a +1 on `sase-ct` — it's a different test than that bead names and isn't covered by `bde727ecc`, so that +1 moved `sase-ct` back to READY.

I made no commit, branch, or PR.

Committed and pushed.

- **Bead**: `sase-fi` was already closed; re-running `sase bead close` reported "Already closed" and appended the verification note without an unpublished-close error, so the close is published.
- **Commit**: `2ac967d78 fix(agents-sync): retry deferred prompt archives on the full sync path`, staging exactly the eight listed files (including the two new ones). The `sase_git_commit` invocation exceeded my 2-minute command ceiling and was killed, so I verified the outcome directly: `git merge-base --is-ancestor` confirms the commit is on `origin/master`, and the working tree is clean. The only side effect of the kill was the leftover `.sase/commit_message.md`, which I removed.

The change gives the full-sync path (`sync_agents`) the prompt-archive rebuild it was missing: it now rebuilds the archives owed by the outbox requests it is about to acknowledge, and leaves a request queued and retryable if the rebuild fails, instead of acknowledging on README materialization alone and discarding the owed prompt.
