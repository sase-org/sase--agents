# Chat History - ace-run (1fj--plan)

- **TIMESTAMP:** 2026-11-23 09:43:00 EST
- **MODEL:** claude/opus
- **AGENT:** 1fj--plan

**Plan:** /home/bryan/.sase/plans/202611/keep_deferred_prompt_sources.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/keep_deferred_prompt_sources.md`

> # Keep deferred prompt-archive sources reachable (monitor turns and dismissals)
> ## Problem
> The `publication/agent_publication` chop reported a digest error on 2026-11-23 at 08:18:
> ```
> gh_bbugyi200__tailnet: could not restore deferred prompt archive for
> bbugyi200.athena.tailnet-1e.7.1.4.1.7.1.7.1.3@de476054ab9e: prompt archive is unresolved
> and a missing local source does not prove there was no prompt obligation
> ```
> One minute later the row was retired as `prompt_archive_unrecoverable` and recorded in
> `~/.sase/agent_publication/terminal_obligations.jsonl`. The terminal machinery from

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. See the
~/.sase/axe/error_digests/digest_20261123_090629_02d8d5da.txt file for context.
%m:@xlarge

## Response

I've written the plan to `sase_plan_keep_deferred_prompt_sources.md`. It's a single-agent tale, size medium. Next I'm validating it.

Validation passes. Next I'm proposing the plan for review.

Yes, this is worth fixing, and I've proposed a plan for it. The plan is a single-agent tale (size medium) and is now waiting for your review.

**What happened:** The agent `tailnet-1e.7.1.4.1.7.1.7.1.3` committed into sase-core at 07:48, which queued a publication row that still needed its `raw_prompt.md`. Its finalizer then failed on a different repo and the agent ended FAILED. At 07:49 it was dismissed from ACE, and the dismiss cleanup deleted its whole artifacts dir, prompt included. The row waited out its 30-minute grace window, raised the digest error at 08:18, and was retired as `prompt_archive_unrecoverable` at 08:19. That prompt is now permanently lost.

**It isn't a one-off.** Every row retired this way since 11-20 (about one a day) has lost its prompt in one of two ways that the earlier fix (`sase-1tz.2.1.6`) didn't cover:

- **Dismissal deletes the prompt (today's error).** Dismiss, kill and the TUI loader's self-heal all delete the artifacts dir without checking whether an active publication row still needs it. The prompt-pool cleanup already has a check like this; agent deletion doesn't.
- **Monitor turns have no prompt (5 of the last 6 errors).** When a monitor turn finishes and the host commits the work, the row points at the monitor's dir, which never contains a prompt. The prompt sits in the dir of the agent that started the monitor, which the restore code never looks at. These errors are guaranteed to happen every time, and those sessions never got a prompt archive.

**The plan:**
1. **Follow monitors to their starter.** Add a small helper that resolves the starter turn's dir. Use it in both the deferred restore and the commit-time archive step, so monitor commits publish the starter's prompt.
2. **Delay deletion while a prompt is still needed.** Dismiss, kill and self-heal leave an artifacts dir in place while an active (not retired, not quarantined) publication row still needs it. That includes a monitor row's starter dir. The agent stays hidden, and the loader's existing retry deletes the dir once the row clears.
3. Add tests for both fixes plus the full dismiss-then-restore case, and update `docs/reference/agents/hood-sync.md`.

Archives that truly can't be rebuilt still retire as before. No sase-core change should be needed.

**Already-retired rows:** four of the retired monitor rows still have their starter prompts on disk, so they could be retried once the fix is installed. The plan lists their keys and the `sase agent sync --retry-retired` command, and notes the retry policy may not pick up retired-prompt rows. Today's tailnet row and `sase-1ux.2` can't be recovered because their dirs are gone.

The dismiss proc's "artifact index sync failed" error at 07:49 is a separate issue and didn't cause the loss; I left it out of scope.
