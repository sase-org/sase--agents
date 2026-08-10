# Chat History - ace-run (research.06.cld)

- **TIMESTAMP:** 2026-08-10 18:12:42 EDT
- **MODEL:** claude/opus
- **AGENT:** research.06.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260810_175914.md`

## Prompt

%id(cld, clan=research.06) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I'm trying to figure out a way to emulate an unprivileged (i.e. can't just commit to master) Github user so I can fork sase and attempt to contribute externally. This would make it way easier to test SASE's collaboration features, which are mostly theoretical at this point. Can you do some research with the goal of helping me figure out the best way to do this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding what SASE's collaboration features actually need to exercise, then look at the GitHub-side options.

The GitHub logic lives in the `sase-github` plugin. Let me open it properly.

Confirmed a decisive fact empirically. Now let me check the comment/review surface and verify GitHub policy details.

All the pieces are verified. Writing the report.

Research written to `sase/repos/research/202608/unprivileged_github_contributor_emulation.md`.

## What I found

**Recommendation: a dedicated GitHub machine account that forks `sase-org/sase`, with its identity selected per-process via `GH_CONFIG_DIR` / `GIT_SSH_COMMAND` / `GIT_AUTHOR_*`.**

Three things drove that, two of which kill the cheaper options:

**1. One account cannot work, at any token scoping.** GitHub hard-blocks a PR author from approving their own PR — no ruleset or scope overrides it. A scoped fine-grained PAT on `bbugyi200` can simulate "push denied," but that's all; approvals, changes-requested, and the first-time-contributor CI gate are all unreachable.

**2. The ToS explicitly allows exactly this.** *"You may maintain no more than one free machine account in addition to your free Personal Account."* Worth naming it for the long term — it's your only one.

**3. SASE will create PRs against the wrong repo today.** This one I measured rather than inferred, using a throwaway local git dir and one of your existing forks:

```
origin=fork only          → gh pr create resolves base to the FORK itself
origin=fork + upstream    → base resolves to the parent, correctly
```

`_clone_gh_repo` clones origin-only, and `ensure_git_clone_at` re-clones the primary and then `set-url`s origin — so extra remotes never propagate to numbered workspaces. Both PR paths (`vcs_mail`, `vcs_create_pull_request`) rely on `gh`'s default base resolution. A fork project would open fork→fork PRs silently, no error. That's a real `sase-github` defect and has to be fixed before anything else is testable.

## The reframe worth flagging

`ws_supports_reviewer_comments` returns `False` for hosted GitHub URLs — *"GitHub does not support reviewer comments via critique_comments."* The `COMMENTS` → CRS machinery is generic and provider-neutral; the GitHub provider just declines to feed it. So the inbound half of the collaboration loop isn't untested, it's **unimplemented**. The machine account is a prerequisite for building it, not just validating it — which argues for provisioning it properly rather than as a throwaway.

Two other consequences you'll want to know about rather than discover: the fork project will auto-create four sidecar repos (`sase--plans`, `--beads`, etc.) on the bot account, since the fork inherits `is_sase_managed: true`; and the first-time-contributor CI approval gate is **perishable** — it stops firing once the bot has one merged PR, so capture that scenario early.

Also confirmed: `master` is currently unprotected with no rulesets, and "Restrict who can push" is free on public repos owned by free orgs — so the maintainer side of the emulation costs nothing to make real.

I did not create, fork, or push anything; all GitHub calls were read-only. Want me to file the `upstream`-remote defect as a task bead via `/sase_new_task`?

I made these changes — the research file is mine from this session. Committing it now.

The log confirms I'm in the research repo. Writing the commit message.

Committed. The research repo is clean and level with `origin/main`.

## Summary

Committed `202608/unprivileged_github_contributor_emulation.md` to the research sidecar as `92a7b3e`, `docs: research emulating an unprivileged GitHub contributor`. `git status --short --branch` shows a clean tree with no divergence from upstream.

The commit message records the recommendation (a dedicated GitHub machine account forking `sase-org/sase`, identity selected per-process via `GH_CONFIG_DIR` / `GIT_SSH_COMMAND` / `GIT_AUTHOR_*`), the reason single-account approaches can't work (GitHub blocks self-approval at any token scoping), and the two code findings — fork projects would silently open fork→fork PRs because no `upstream` remote reaches a numbered workspace, and GitHub reviewer comments are unimplemented rather than merely untested.

One thing to note: the commit itself succeeded, but prompt-archive publication was deferred because the agents sync lock was busy, and the project now has 2 quarantined agent-hood publication requests. The archive link on this commit may stay unavailable until you run `sase agent sync --retry-quarantined`. I did not run that — it touches shared agent state beyond this commit.

The `upstream`-remote defect in `sase-github` is still unfiled; say the word and I'll take it through `/sase_new_task`.
