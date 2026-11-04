# Chat History - ace-run (sase-1r5--plan)

- **TIMESTAMP:** 2026-11-04 06:50:45 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1r5--plan

**Plan:** /home/bryan/.sase/plans/202611/github_publickey_retry.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/github_publickey_retry.md`

> # Plan: Retry transient GitHub SSH publickey denials
> ## Context
> From about 09:37 UTC on 2026-11-04, GitHub intermittently rejected valid, registered SSH
> keys with `Permission denied (publickey)`. The same key flipped between success and
> denial within minutes on two hosts with different keys and different routes
> (`github.com:22` and `ssh.github.com:443`). Each rejection killed an agent launch in
> workspace preparation:
> ```
> run_agent_runner_launch._prepare_workspace_and_repos
>   -> axe.runner_workspace_protection.prepare_launch_workspace_repos   (strict for workspace > 1)

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase
%id(sase-1r5, bead=sase-1r5)
%m:@xlarge
Can you complete the work for task bead sase-1r5 by running the `sase bead read sase-1r5 -r "Need the task scope"` command,
reviewing the command's output, doing the work, and then closing the bead by running the
`sase bead close sase-1r5 --note "<what you verified>"` command?

If the host notice says the task bead was already closed when this run started, the run is attached to the closed
bead. Only the host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you
copied the wrong ID — re-copy `sase-1r5` from this prompt before concluding anything. Check whether the
earlier work landed before redoing anything, and run `sase bead open sase-1r5` only if the work is genuinely
unfinished. The `sase bead close` step is then a safe no-op or the real close.

If you discover genuinely distinct follow-up work that is outside this task, use `/sase_new_task` with details
identifying the current bead; it will corroborate a duplicate, attach a causally related active-epic issue, or
create a sized task as appropriate.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

Reading the bead's scope is done; I'm now exploring the sase-core classifier and the sase call sites so I can author the plan.

Still mapping call sites: I've covered the SDD clone and network-git retry paths, and next I'll look at `github_cli`, the workspace lease fetch, and the auth consumers.

Checking whether the sase-github plugin also consults the shared classifier before I settle the call-site inventory.

Tracing the launch-path deadline that would cap a longer auth-retry budget, then I'll write the plan.

Nearly done exploring: checking how launch treats a transient materialization failure, since that decides what an exhausted auth budget should raise.

I have what I need for the plan. Next I'll write a draft and run the validator with `--explain` to get the exact epic schema.

Validation passed. One label is inconsistent with the body (the five-minute option is 9 attempts, not 8), so I'll fix it and revalidate.

Validation passes. Submitting the plan for review.

The proposal is staged. Finishing the turn through `/sase_final`.

I've written a plan for sase-1r5 and submitted it for your review, but no code has changed yet. I left the bead open, because closing it now would claim work that hasn't happened. The coding starts once you approve the plan.

**What's going wrong:** sase-core's shared failure classifier treats `Permission denied (publickey)` as a permanent authentication failure. So the SDD store clone in `_store_clone_remote.py` gives up on the first denial instead of retrying, and the launch dies. The same thing broke the `agent_publication` and `external_issue_mirror` jobs during the incident.

**Proposed fix:** add a new classifier result, `credential_unconfirmed`, used only for publickey denials on `git` and `git clone` (not `gh`). It still counts as "not retryable", so any code that doesn't explicitly opt in keeps failing fast as it does today. Its reason keeps the `authentication:` prefix, so the ssh-agent hint and the mirror's `auth_error` label keep working. The change is additive, so mismatched old and new versions of sase and sase-core still behave correctly together.

The plan has five phases:
1. **sase-core:** add the new result and mark deploy-key refusals as permanent authentication failures, with tests.
2. **sase:** move the sase-core pin forward, and add one shared retry helper. It respects deadlines, has a short budget for background jobs and a longer one for launches, and has a `SASE_GIT_CREDENTIAL_RETRY_MAX_SECONDS` kill switch (`0` turns retries off). It fails immediately when the host has no SSH key or agent at all. After one operation uses up its budget, later ones to the same host stop retrying for 10 minutes, so a launch cloning several stores doesn't wait out the full budget for each.
3. **SDD store clone:** use the helper. A test uses a fake GitHub that denies N times and then serves a real repo, so it needs no network.
4. **Agent-publication git and workspace-lease fetch:** use the helper, replacing the lease fetch's own one-off 10s retry.
5. **Docs and follow-ups:** document the behaviour and note follow-ups for git operations that don't use the classifier yet (bead sync, finalizer push, sidecar git).

`ssh_agent.py` and `_sync_logs.py` don't use this classifier, so they stay as they are and keep reporting real credential problems promptly.

**Two choices for you when you approve:**
- **How long a launch keeps retrying:** about 2 minutes by default (6 attempts). The cost is that a genuinely wrong key fails a launch about 2 minutes later than today. The alternatives are about 5 minutes or about 30 seconds.
- **Whether to also mark deploy-key refusals as permanent authentication failures:** yes by default. That's the classifier part of sase-167; that bead keeps the rest of its work.
